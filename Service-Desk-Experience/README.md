# Service Desk Experience: Skills & Volume Summary

Rather than list individual tickets, this section aggregates real production support experience into skill domains, reflecting the breadth and volume of hands-on IT work performed in a HIPAA-regulated healthcare environment, first as a Service Desk Technician and now as an IT Support Specialist.

> **Data handling note:** Every example below is generalized. No requester names, email addresses, phone numbers, ticket IDs, partner organization names, system identifiers, or free-text ticket content appear in this repository. Raw exports are kept outside this repository entirely. Themes and volume only, never rows.

---

## Volume Snapshot

**August 2026, individual performance:**

- **56 tickets handled, 54 resolved**
- **Roughly 96% individual resolution rate**
- **Roughly 23% of total team ticket volume** for the month

These are my individual figures, not team totals. I handled close to a quarter of what the Service Desk processed that month while resolving at a rate above my own handled count would suggest, meaning very little of my queue moved on to someone else.

**Ongoing:**

- Mix of standard break/fix work and formal Service Requests, handled through distinct workflows
- Priority range from Low through High, with escalation paths for issues blocking clinical or client-facing staff
- Consistent same-day or next-day resolution on the majority of standard requests

---

## Skill Domains Demonstrated

### 1. Identity & Access Management
- Password resets and account lockout resolution following identity-verification procedure
- Multi-factor authentication enrollment, re-enrollment, and recovery for users who lost their enrolled device
- Account access lifecycle: provisioning at onboarding, suspension for extended leave, and revocation at termination, where timing matters for compliance
- Email alias administration and mailbox delegation
- Distinguishing credential failures from conditional access blocks from licensing gaps, which are three different fixes behind one identical error message

### 2. SaaS Application Provisioning & Access Lifecycle
- User provisioning across CRM, workforce management, compliance, and analytics platforms, following IT-owned provisioning processes rather than ad hoc grants
- Admin consent request handling for third-party application integrations, including requests that expired before approval and had to be reassessed rather than rubber-stamped
- Elevated access provisioning where the business case justified a higher permission tier
- Software approval review for user-requested applications, including licensing and installation

### 3. Enterprise Platform Administration
- Internal administrator for the organization's work management platform, covering permissions, board and workflow configuration, forms, and dashboards. See [monday.com Platform Administration](../Enterprise-Applications/Monday-Platform-Administration.md)
- Internal administrator for an in-house AI platform
- Permission architecture work: identifying which specific permission gates a requested capability rather than escalating a user to full admin to unblock them

### 4. Endpoint, VDI & Application Support
- VDI session troubleshooting at volume: connection and login failures, sessions stuck restoring, session lag, disconnects, and profile or cache resets
- Audio and headset diagnostics inside virtualized sessions, including one-way audio, output routing to the wrong device, and call quality degradation. See the [VDI Session Degradation investigation](../Experience-Journal/Endpoint-Diagnostics/VDI-Session-Degradation.md) for the deep-dive version
- Microsoft 365 troubleshooting: Outlook, Teams, OneNote and OneDrive sync
- Browser runtime and client component failures preventing access to conferencing and virtualization clients
- Endpoint hardware triage, replacement coordination, and new device setup including full user migration
- Wireless and connectivity troubleshooting, including secure web gateway client drops affecting live calls

### 5. Cloud-Hosted Internal Application Support
- Supporting internally built applications deployed to cloud-hosted static app infrastructure
- Source control repository access administration for internal application work
- Deployment troubleshooting, including custom domain and certificate provisioning and failures the automated pipeline could not resolve
- Application ownership continuity planning when an owner goes on extended leave

### 6. Client & Partner System Access Support
- Troubleshooting access for staff who require connectivity to **partner health system platforms** via VDI and Citrix-based access into external organizations' environments
- Coordinating across multiple stakeholder teams when an issue spans internal IT and a partner organization's help desk, including cases where the fix was entirely on the partner side and the job was accurate diagnosis plus a clean handoff

---

## Why This Matters For An Infrastructure Path

This volume of front-line troubleshooting built the diagnostic instinct that shows up directly in the project work elsewhere in this repo.

The clearest example: in the [AppLocker Isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md), a Tanium computer group preview returned **0 of 0 members**. The obvious read is a broken configuration, and the obvious response is to tear it down and rebuild. Instead I recognized the shape of a normal sensor and heartbeat evaluation lag, waited for a refresh cycle, and it resolved to 1 of 1. That's not Tanium knowledge, since I didn't have any yet. It's the root-cause-first habit built from a few thousand tickets where the first symptom was rarely the actual problem.

Service desk work also taught me the cost of over-restricting access, which is exactly the tension in the [Dynamic Travel Access](../Experience-Journal/Cloud-Projects/Dynamic-Travel-Access-Provisioning.md) design: every unnecessary approval gate becomes a ticket, a delay, and a blocked clinician. Security controls that ignore that cost get worked around.

---

## How This Section Updates

Volume and themes are refreshed as new reporting comes in, **without ever storing requester-identifiable data in this repository.** Raw exports live outside the repo and are blocked by [.gitignore](../.gitignore).
