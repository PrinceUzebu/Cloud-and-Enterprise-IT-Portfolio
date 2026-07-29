# Cloud Projects

Production engineering work, not lab exercises. Each write-up covers the business problem, the design decisions and why I made them, the implementation log, and what I'd do differently.

| Project | Status | Domain | Summary |
|---|---|---|---|
| [Offshore Engineer Isolation & AppLocker Hardening](./AppLocker-Isolation.md) | ✅ Complete, pending final security sign-off | Endpoint Security · Application Control · Privileged Access Management · Tanium Enforce | Designed and implemented a technically-enforced isolation boundary for a third-party contractor VM, enforced by policy rather than trust |
| [Dynamic Travel Access Provisioning](./Dynamic-Travel-Access-Provisioning.md) | 🔄 In Progress, design & feasibility | Identity & Access Management · Entra ID · Endpoint Policy | Designing a dynamic Entra ID group model to auto-provision and auto-revoke elevated device access for traveling employees |

---

## What These Have In Common

Both projects sit at the same seam: an **identity system** on one side, an **endpoint policy engine** on the other, and a security requirement that only holds if the two stay in sync. The AppLocker project solved that seam by deliberately *not* automating it (static group, human-gated membership). The travel access project is the inverse problem, because automation is the whole point when manual revocation is what fails.

Knowing which of those two answers a given problem needs is the actual skill I'm building here.
