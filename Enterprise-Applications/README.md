# Enterprise Applications

Line-of-business application support and administration in a healthcare environment. Application and partner organization names are generalized per this repo's [data-handling standard](../docs/CONTRIBUTING.md).

---

## Healthcare Clinical Systems

**Credentialed Epic Trainer**, see [Certifications](../Certifications/)

Delivering end-user training and enablement on a major healthcare EHR platform. The relevant skill here isn't the application, it's translating technical change into language a clinician under time pressure can actually act on. That's a distinct competency from knowing the system, and it's the reason the [AppLocker project documentation](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md) could serve a security engineering audience and an IT leadership audience in the same document.

- EHR application training delivery and end-user enablement at scale
- Access and account troubleshooting for clinical staff
- Coordinating access into **partner health system platforms**, where staff work inside an external organization's environment via VDI/Citrix, including issues where the resolution lived entirely with the partner's help desk and the job was accurate diagnosis plus a clean handoff

---

## Business Platforms Supported

Generalized by category rather than product name:

| Category | Support Provided |
|---|---|
| **Project / work management platform** | Administrative support through a company-wide rollout: user enablement, board and workspace structure, training, and troubleshooting during adoption |
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

- [ ] Document an application integration or SSO configuration project end to end
- [ ] Write up an application access review cycle, tying into the [IAM](../Experience-Journal/IAM/) and [PAM](../Experience-Journal/Privileged-Access-Management/) sections
