# Monday.com Platform Administration
### Internal IT Administrator for an enterprise work management platform

**Role:** Internal Monday.com IT Administrator, held alongside my IT Support Specialist role
**Since:** July 2026
**Scope:** Company-wide platform administration, configuration, build, and support

> *Note on detail level: no board names, workspace structures, business processes, user names, or platform data appear here. What's described is the shape of the work and the responsibilities I hold, not the content of anyone's boards.*

---

## What I Own

I'm the primary internal administrator and the first point of contact for Monday.com across the organization. Every platform request, permission change, build question, and problem report routes to me before it goes anywhere else.

I work under the mentorship of an external Monday.com consultant, and the arrangement is deliberately structured so that I take on more independent ownership over time rather than staying a permanent escalation layer. That's the trajectory: from supported administrator to independent platform owner.

The responsibility covers five areas.

### 1. Platform Administration

Account-level administration: user provisioning and deprovisioning, seat management, permission assignment, and access scoping at the board and workspace level. This is identity and access management wearing different clothes, and it uses the same reasoning as the Entra ID work elsewhere in this repo: who needs access, at what level, for how long, and who decides.

### 2. Build and Configuration

Building and configuring boards, workflows, and automations to match how a team actually works. The technical part is rarely the hard part. The hard part is that the first version of a requested workflow is usually a description of the current manual process, and a direct translation of a manual process into a platform tends to reproduce its problems at higher speed.

### 3. Forms and Dashboards

Building intake forms and reporting dashboards. Forms are where data quality is won or lost, since a field that's ambiguous at intake produces a board that can't be reported on later. Dashboards are where the platform proves its value to leadership, which means they have to answer the question that was actually asked.

### 4. Requirements Translation

Working with teams to turn a business need into something the platform can do. This is the part I find most transferable. A request arrives as an outcome ("I need to track X across these teams"), and the work is converting it into structure: what's a board, what's a group, what's an item, what's a subitem, what's an automation, and what should stay outside the platform entirely.

### 5. User Support and Enablement

Front-line support for the platform: troubleshooting, permission and access issues, and helping people use capability that already exists. A meaningful share of platform tickets are not defects. They're capability gaps, where the user needs a permission they don't have or doesn't know a feature exists. Telling those apart quickly is most of the job.

---

## Representative Work

Generalized. No board names, business processes, or requesters.

| Request type | What the work involved |
|---|---|
| **Permission elevation for advanced board structures** | Users needing to build multi-level boards with nested subitems lacked the permission tier to do so. Required understanding which permission actually gates the capability, rather than escalating everyone to admin |
| **Board duplication across workspaces** | Duplicating a board into a different workspace for planning work, with correct permission scoping at the destination so a planning copy doesn't inherit or leak production access |
| **Workspace placement decisions** | Deciding where a board should live when the requester genuinely didn't mind, which is a governance question rather than a preference one |
| **Access provisioning and onboarding** | Adding users to the platform with appropriate scope as part of broader onboarding, coordinated with the identity and licensing side |
| **Platform troubleshooting** | Diagnosing whether a reported problem is a defect, a permission gap, a configuration issue, or a feature the user hasn't been shown |

---

## Why This Belongs In An Infrastructure Portfolio

Enterprise SaaS administration is not a detour from infrastructure work. It's the same problem set applied to a platform instead of a server:

- **Identity and permissions.** Who can do what, scoped correctly, reviewed over time. The same reasoning as Entra ID group design.
- **Change control.** A permission change on a shared board affects everyone on it immediately. There's no staging environment for a live workspace, which forces the same clone-before-edit discipline I used in the [AppLocker isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md).
- **Governance.** Structure decisions made early become very expensive to reverse once teams have built on them.
- **Single accountable owner.** Being the person a platform routes to changes how carefully you work. There's no second reviewer to catch a scoping mistake before it lands.

---

## Skills This Is Building

- Enterprise SaaS platform administration and governance
- Permissions architecture and access scoping at platform level
- Workflow, automation, and form configuration
- Dashboard and reporting design against real stakeholder questions
- Requirements gathering and translation from business need to technical structure
- Change management on a live, shared, company-wide system
- Working under technical mentorship while taking increasing independent ownership

---

## Certification Track

Both currently in progress, neither complete. See [Certifications](../Certifications/).

- **Monday Work Management Core Certification**, covering the build and configuration side
- **Monday.com Admin Certification**, covering account administration, permissions architecture, and governance

---

## Roadmap

- [ ] Document a permission model design end to end, sanitized
- [ ] Document an automation or workflow build from requirement through delivery
- [ ] Build out a platform governance reference: naming conventions, workspace structure standards, and an access review cadence
- [ ] Complete both certifications and update this page with what changed in how I work
