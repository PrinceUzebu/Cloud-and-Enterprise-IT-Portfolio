# Cloud Projects

Production engineering work, not lab exercises. Each write-up covers the business problem, the design decisions and why I made them, the implementation log, and what I'd do differently.

| Project | Status | Domain | Summary |
|---|---|---|---|
| [A Reported Azure AD Failure That Was an Application Defect](./Static-Web-App-Save-Failure.md) | ✅ Resolved | Azure Static Web Apps · Entra ID · Root Cause Analysis | Total save failure reported as an expired Entra ID client secret. Traced it to an accumulating-state defect that had grown the stored document to 1.2 MB, restored service, and fixed the underlying bug |
| [Offshore Engineer Isolation & AppLocker Hardening](./AppLocker-Isolation.md) | ✅ Complete, pending final security sign-off | Endpoint Security · Application Control · Privileged Access Management · Tanium Enforce | Designed and implemented a technically-enforced isolation boundary for a third-party contractor VM, enforced by policy rather than trust |
| [Dynamic Travel Access Provisioning](./Dynamic-Travel-Access-Provisioning.md) | 🔄 In Progress, design & feasibility | Identity & Access Management · Entra ID · Endpoint Policy | Designing a dynamic Entra ID group model to auto-provision and auto-revoke elevated device access for traveling employees |

---

## What These Have In Common

The first plausible answer is wrong in all three, and in a different way each time.

On the **save failure**, the reported cause was specific, well evidenced, and incorrect. The fix was in the application, not the infrastructure the report pointed at.

On the **AppLocker isolation**, the obvious implementation was a dynamic group. I rejected it, because a boundary that re-evaluates its own membership can move without anyone deciding to move it.

On **travel access**, the obvious fix was to loosen the policy for anyone who might travel, which converts a temporary exception into a permanent one. That project also reaches the *opposite* conclusion about dynamic groups from the AppLocker project, and deliberately so: when silent drift is the main risk you remove automation, and when failure to revoke is the main risk automation is the control.

Two of these are about designing something. One is about refusing to accept a diagnosis. The common skill is the same either way, which is being willing to spend time on the answer that is less convenient than the one already on the table.
