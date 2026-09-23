# A Reported Azure AD Failure That Was an Application Defect
### Diagnosing total save failure on an internally built Azure Static Web App

**Status:** ✅ Resolved. Service restored, root cause fixed, confirmed by the application owner
**Domain:** Azure Static Web Apps · Entra ID · Application Diagnostics · Root Cause Analysis

> *Note on detail level: the application name, its URL, the partner organization it reports on, and the requester are omitted. Error behavior, reasoning, and measurements are unchanged from the real incident.*

---

## Summary

An internally built status reporting application, hosted on Azure Static Web Apps, stopped saving for every user. The application owner reported it with an unusually good writeup: reproduced across multiple browsers, reproduced in private windows, reproduced after clearing cookies, with browser console errors captured. He had already concluded the cause and named it specifically as an expired Entra ID client secret behind the Static Web App's built-in authentication, and he listed the exact portal blades he wanted checked.

It was a credible diagnosis supported by real evidence. It was also wrong.

The actual cause was an application defect. Every time a report was published, the app embedded a full copy of all previously published reports inside the new one, so the stored document doubled with each publish until the backend began rejecting writes. I pruned the accumulated data to restore service, then fixed the underlying bug so it could not recur.

---

## Why This One Is Worth Writing Up

Because the hard part was not the fix. The hard part was not accepting a well-argued answer from someone who had clearly done their homework.

A confident, specific, evidence-backed diagnosis from a technical requester is the easiest thing in the world to just go and confirm. Open the blade, look at the secret, rotate it if it looks stale, move on. That path was available and it would have felt like diligence.

---

## The Observation That Killed the Reported Diagnosis

**Reads worked. Only writes failed.**

That single asymmetry is fatal to the client secret theory. An expired secret breaks authentication, and broken authentication breaks the entire session. If the token were invalid the user could not have loaded the application at all, let alone opened it, viewed existing reports, and then hit an error only at the moment of saving.

Everything still worked right up until the write. So whatever was failing had to sit downstream of authentication, in what the application was doing with the payload rather than in who it claimed to be.

Once that was established, the portal blades the requester asked me to check were no longer where the answer lived. I checked them anyway, because confirming a negative is cheap and I wanted it on record, and the secret was valid.

---

## Environment & Constraints

| Item | Detail |
|---|---|
| Platform | Azure Static Web Apps, internally built line-of-business application |
| Authentication | Entra ID via the platform's built-in authentication provider |
| Reported symptom | Save failing for all users, all browsers, all machines |
| Ruled out by requester | Local session state, cookies, browser-specific behavior, single-machine issues |
| Reported cause | Expired or rotated Entra ID client secret |
| Business impact | Blocked weekly status reporting for a partner health system engagement |
| Deployment path | Source control with an automated deployment pipeline |

---

## Investigation

| Step | Action | Finding |
|---|---|---|
| 1 | Reviewed the reported evidence | Genuinely thorough. Cross-browser and private-window reproduction correctly eliminated client-side state, so the fault was server-side or application-side |
| 2 | Tested the read path | Application loaded, authenticated, and displayed existing report history normally. This is the finding the rest of the investigation turns on |
| 3 | Checked the app registration anyway | Client secret valid and unexpired. Confirmed the reported diagnosis was incorrect rather than merely unproven |
| 4 | Verified the identity provider configuration | Unchanged. No recent modification to the authentication setup |
| 5 | Inspected the stored document | Found the payload had grown to **1,246,180 bytes**, with the overwhelming majority of it duplicated content |
| 6 | Traced the growth pattern | Each publish serialized the full existing report history into the new record, so every publish roughly doubled the stored size. Growth was compounding, not linear |
| 7 | Correlated with the failure | The write was being rejected on size. Reads were unaffected because reading a large document is not subject to the same limit |

---

## Root Cause

An accumulating-state defect in the publish routine. The application wrote each new report as a record that contained the entire prior history nested inside it, rather than appending an entry to a collection.

That makes size growth compounding. The application works perfectly for a long time, then fails abruptly and totally the moment it crosses a threshold. There is no gradual degradation to warn anyone, which is exactly why it presented as a sudden platform-level outage and why an infrastructure cause looked so plausible.

The failure was also **silent**. The save was rejected but the application surfaced only a generic connection error, giving the user no signal about what had actually gone wrong.

---

## Resolution

Two stages, deliberately in this order.

**1. Restore service.** Exported the stored document using the application's own export function before touching anything, then pruned the nested duplicate history.

- Before: **1,246,180 bytes**
- After: **42,120 bytes**
- **96.6% reduction**, and saving worked immediately

The export came first because I had no guarantee the prune would go cleanly and no way to reconstruct the data if it did not.

**2. Fix the cause.** Corrected the publish routine so it no longer embeds prior history in each new record, and deployed the fix. Also surfaced the real backend error in the UI, so that a rejected save reports what actually failed rather than a generic connection message.

**Data integrity:** all outcomes, activities, milestones, risks, and published report history were preserved. Nothing was lost. I confirmed this explicitly to the owner unprompted, because it was the thing he was going to worry about whether or not he asked.

---

## Outstanding Items

Recorded rather than quietly closed.

- **Retained history still grows, just linearly now.** The compounding behavior is gone, but the document will keep growing as reports accumulate. There is ample headroom, and a retention cap is a data-owner decision rather than a technical one, so it was raised with the owner rather than imposed.
- **Other applications built on the same pattern.** If this publish routine came from a shared template, the defect is not in one application, it is in the template, and the others simply have not crossed the size threshold yet. This is the highest-value follow-up and it is proactive work rather than incident response.
- **A stale repository warning** on the platform's authentication blade. Deployments succeed through the pipeline token, so this is cosmetic. Documented so nobody burns time chasing it later.

---

## Skills Demonstrated

- Root cause analysis that contradicted a confident, well-evidenced reported diagnosis
- Using behavioral asymmetry (reads succeeding while writes failed) to eliminate an entire layer from consideration
- Azure Static Web Apps and Entra ID authentication configuration review
- Checking a negative rather than skipping it, so the eliminated cause is documented instead of assumed
- Backing up before destructive remediation
- Separating service restoration from defect correction, and sequencing them correctly
- Converting a silent failure into a reported one
- Explaining a technical root cause in plain language to a non-engineer without either condescending or burying them

---

## Lessons Learned

- **The quality of a diagnosis is not the same as its correctness.** This report was better written than most, and the confidence it carried made the wrong answer more persuasive, not less. Good evidence deserves respect and still has to be tested.
- **Ask what still works, not just what broke.** The functioning read path was more diagnostically useful than the failing write path, because it eliminated a whole layer in one observation. The working half of a system is evidence.
- **Compounding growth fails like an outage.** Anything that doubles will look fine indefinitely and then break completely, with no warning period. That failure shape is worth recognizing on sight, because it invites infrastructure explanations for application problems.
- **A silent failure is a second defect.** Fixing the growth without fixing the error reporting would have left the next failure just as hard to diagnose.
