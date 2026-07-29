# Security & Incident Response

Security-relevant escalations and incident response participation, generalized and anonymized consistent with this repository's [data-handling standard](../../docs/CONTRIBUTING.md).

---

## Status: Building This Section

I'm being deliberate about this one. Incident write-ups are the easiest section of a portfolio to pad with things that weren't really incidents, and the hardest to write about honestly without disclosing detail that shouldn't be public. So rather than backfill thin content, this section fills in as I participate in work substantial enough to be worth documenting.

What's here now is the security-adjacent judgment I can show from completed project work.

---

## Security Judgment Demonstrated Elsewhere In This Repo

| Situation | What It Demonstrates |
|---|---|
| [Escalating EDR agent removal](../Cloud-Projects/AppLocker-Isolation.md) instead of stripping it | Recognizing that removing endpoint protection from a machine is a compensating-control decision requiring security sign-off, not a cleanup task |
| [Flagging a data-exfiltration path](../Cloud-Projects/AppLocker-Isolation.md) on a contractor VM | Identifying non-Microsoft cloud storage and FTP clients on an externally-operated machine as exfil risk rather than harmless utilities |
| [Flagging an attention-tracking utility](../Cloud-Projects/AppLocker-Isolation.md) | Catching monitoring software that was inappropriate for a contractor-facing machine on privacy grounds, not just security grounds |
| [Refusing to strip an unidentified hash rule](../Cloud-Projects/AppLocker-Isolation.md) | Not guessing on a rule with no identifiable purpose. Flagged for review rather than removed blind |

---

## Planned

- [ ] Write-up of a phishing / credential-compromise response, from triage through containment
- [ ] Home lab: Microsoft Defender for Endpoint alert triage walkthrough
- [ ] Home lab: Entra ID sign-in log investigation — what a real impossible-travel alert looks like end to end
- [ ] Reference: incident severity classification and escalation criteria
