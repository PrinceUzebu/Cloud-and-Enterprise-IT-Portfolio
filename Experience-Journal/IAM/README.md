# Identity & Access Management

This section indexes the IAM-focused work across the portfolio, plus the concepts each piece demonstrates.

| Work | IAM Concept Demonstrated |
|---|---|
| [Offshore Engineer AppLocker Isolation](../Cloud-Projects/AppLocker-Isolation.md) | Static group-based access boundary, explicit exclusion over implicit non-targeting |
| [Dynamic Travel Access Provisioning](../Cloud-Projects/Dynamic-Travel-Access-Provisioning.md) | Entra ID dynamic groups, membership rule logic, conditional-access-adjacent design |
| [Privileged Access Management](../Privileged-Access-Management/) | Elevated and third-party access scoping, least privilege applied to contractors |
| [Service Desk Experience](../../Service-Desk-Experience/) | MFA enrollment, password and account lifecycle management at volume |

---

## The Through-Line

Most of my IAM work so far has centered on one question: **when should access be automatic, and when should a human have to sign off?**

Front-line service desk work taught me the cost of getting that wrong in the friction direction. Every unnecessary approval gate is a ticket, a delay, and a frustrated clinician. The AppLocker isolation project taught me the cost of getting it wrong in the other direction, where automated membership evaluation on a security boundary means the boundary can silently move without anyone deciding to move it.

The answer isn't a policy, it's a judgment about which failure mode you can least afford in a given control. That's the reasoning I'm trying to build deliberately, not just the tooling knowledge.

---

## Roadmap

- [ ] SC-300 (Identity and Access Administrator) study notes
- [ ] Home lab: Conditional Access policy simulation, including break-glass account design
- [ ] Home lab: Entra ID dynamic group rule-writing reference sheet
- [ ] Write up access review and lifecycle management work as it comes in
