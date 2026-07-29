# Enterprise Applications

Line-of-business application support and administration in a healthcare environment. Partner organization names are generalized in line with employer data-handling policy.

---

## Platform Ownership

**Sole IT Administrator, Monday.com and in-house AI platform** (July 2026 to present)

As of July 2026 I own IT administration for two enterprise platforms outright, rather than supporting them as one technician among several. This is the first work where I'm the single accountable owner of a platform rather than a contributor to it.

### Monday.com (Work Management Platform)

Sole IT administrator for the organization's work management platform, following earlier involvement in its company-wide rollout.

- User and permission administration: account provisioning, seat assignment, and board/workspace access scoping
- Single escalation point for platform issues across the organization
- End-user enablement and troubleshooting
- Access coordination as part of onboarding and offboarding

Being the only admin changes how you work. There's no second person to sanity-check a permission change before it affects everyone on a board, so the discipline from the [AppLocker isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md) transfers directly: understand the current state before changing it, and don't make a change you can't explain or reverse.

### In-House AI Platform

Sole IT administrator for the organization's internally developed AI assistant. This is where my **Azure AI Fundamentals (AI-900)** credential moves from certification into applied administration.

- Access administration and user provisioning
- Front-line support and troubleshooting for end users
- End-user enablement across a platform most staff are encountering for the first time

Supporting an internal AI tool is a genuinely different support problem from supporting a conventional application. With Outlook, a user reporting that something is broken usually means something is broken. With an AI assistant, the same report often means the output was unexpected rather than wrong, and the work is establishing which of the two you're dealing with before troubleshooting anything. Knowing where model behavior ends and platform misconfiguration begins is the skill this role is building.

*Both sections will be expanded with specific projects and configuration work as I take them on.*

---

## Healthcare Clinical Systems

**Credentialed Epic Trainer**, see [Certifications](../Certifications/)

Delivering end-user training and enablement on a major healthcare EHR platform. The relevant skill here isn't the application, it's translating technical change into language a clinician under time pressure can actually act on. That's a distinct competency from knowing the system, and it's the reason the [AppLocker project documentation](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md) could serve a security engineering audience and an IT leadership audience in the same document.

- EHR application training delivery and end-user enablement at scale
- Access and account troubleshooting for clinical staff
- Coordinating access into **partner health system platforms**, where staff work inside an external organization's environment via VDI/Citrix, including issues where the resolution lived entirely with the partner's help desk and the job was accurate diagnosis plus a clean handoff

---

## Other Business Platforms Supported

Generalized by category rather than product name:

| Category | Support Provided |
|---|---|
| **HRIS / timekeeping** | Access provisioning, authentication troubleshooting, and role-change coordination |
| **Contact center platform** | Client installation, configuration, and audio/connectivity troubleshooting for client-facing staff |
| **BI / analytics tooling** | Access provisioning and report-availability troubleshooting |
| **Credential management** | Enrollment support and recovery workflows |

---

## The Pattern Across All Of Them

Every one of these platforms produced the same class of ticket: **a user-facing symptom that maps to several unrelated root causes across different layers.** "I can't get into the system" is identity, licensing, network path, client version, or the vendor's outage, and the fix is completely different in each case.

Doing this across five or six platforms is what built the habit of isolating the failing layer before touching anything, which is the single most transferable skill from application support into infrastructure work.

---

## Roadmap

- [ ] Document a Monday.com administration project end to end (permission model design, or automation build)
- [ ] Document AI platform enablement work: what the common support patterns turn out to be, and what actually reduces them
- [ ] Document an application integration or SSO configuration project end to end
- [ ] Write up an application access review cycle, tying into the [IAM](../Experience-Journal/IAM/) and [PAM](../Experience-Journal/Privileged-Access-Management/) sections
