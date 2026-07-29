# Service Desk Experience: Skills & Volume Summary

Rather than list individual tickets, this section aggregates real production support experience into skill domains, reflecting the breadth and volume of hands-on IT work performed as a Service Desk Technician in a HIPAA-regulated healthcare environment.

> **Data handling note:** Every example below is generalized. No requester names, email addresses, phone numbers, ticket IDs, partner organization names, or free-text ticket content appear in this repository. Raw exports are kept outside this repository entirely. Themes and volume only, never rows.

---

## Volume Snapshot

- **100+ tickets resolved** across a rolling sample period (spring to summer 2026)
- Mix of standard **Service Desk** break/fix work and formal **Change Requests**, handled through distinct workflows
- Priority range from Low through High, with escalation paths for issues blocking clinical or client-facing staff
- Consistent same-day or next-day resolution on the majority of standard requests

---

## Skill Domains Demonstrated

### 1. Identity & Access Management
- Password resets and account lockout resolution following identity-verification procedure
- Multi-factor authentication enrollment, re-enrollment, and recovery for users who lost their enrolled device
- VDI account provisioning and access troubleshooting
- New-hire and role-change access coordination across multiple systems
- Distinguishing credential failures from conditional access blocks from licensing gaps, which are three different fixes behind one identical error message

### 2. End-User Application & Device Support
- Microsoft 365 troubleshooting: Outlook profile and access issues, Teams client failures, OneNote and OneDrive sync problems
- Audio/video conferencing diagnostics across multiple platforms, covering headset and camera detection, one-way audio, and client-vs-VDI-specific failure modes
- VDI performance and session issues: slow load, unexpected disconnects, session persistence, cache and profile resets
- Endpoint hardware triage, replacement coordination, and escalation
- Wireless connectivity troubleshooting on both corporate and home networks

### 3. Enterprise Application Administration
- Distribution list and shared mailbox delegation configuration
- Administrative support for an internal project-management platform rollout, including user enablement and training
- Cross-application access coordination for client-facing clinical staff tooling
- HRIS and timekeeping platform access support

### 4. Change Management & Provisioning
- New-hire equipment provisioning workflows end to end
- Structured Change Request handling, kept deliberately separate from break/fix ticket flow
- Onboarding and offboarding task coordination across IT and HR-adjacent systems
- Termination-day access revocation coordination, where timing matters for compliance

### 5. Client & Partner System Access Support
- Troubleshooting access for staff who require connectivity to **partner health system platforms** (VDI and Citrix-based access into external organizations' environments)
- Coordinating across multiple stakeholder teams when an issue spans internal IT and a partner organization's help desk, including cases where the fix was entirely on the partner side and the job was accurate diagnosis plus a clean handoff

---

## Why This Matters For A Cloud Engineering Path

This volume of front-line troubleshooting built the diagnostic instinct that shows up directly in the project work elsewhere in this repo.

The clearest example: in the [AppLocker Isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md), a Tanium computer group preview returned **0 of 0 members**. The obvious read is a broken configuration, and the obvious response is to tear it down and rebuild. Instead I recognized the shape of a normal sensor/heartbeat evaluation lag, waited for a refresh cycle, and it resolved to 1 of 1. That's not Tanium knowledge, since I didn't have any yet. It's the root-cause-first habit built from a few thousand tickets where the first symptom was rarely the actual problem.

Service desk work also taught me the cost of over-restricting access, which is exactly the tension in the [Dynamic Travel Access](../Experience-Journal/Cloud-Projects/Dynamic-Travel-Access-Provisioning.md) design: every unnecessary approval gate becomes a ticket, a delay, and a blocked clinician. Security controls that ignore that cost get worked around.

---

## How This Section Updates

New ticket data is aggregated into this summary on a rolling basis. Volume and themes get refreshed as new export data comes in, **without ever storing requester-identifiable data in this repository.** The raw exports live outside the repo and are blocked by [.gitignore](../.gitignore).
