# Tools & Automation

Scripts and automations built to cut out repetitive manual work. Everything here is sanitized: no tenant identifiers, hostnames, credentials, or internal endpoints.

**Status:** 🔄 Building. Scripts land here once they've actually run against something real.

---

## PowerShell

The automation surface I'm targeting first, since it's where enterprise Windows and M365 administration actually lives.

- [ ] **Exchange Online reporting** — mailbox permission and delegation audit across the tenant, because tracing "who has access to this shared mailbox" by hand does not scale
- [ ] **Entra ID group membership export** — snapshot group membership for access review cycles, relevant to the [IAM roadmap](../Experience-Journal/IAM/)
- [ ] **Bulk user provisioning** — new-hire account creation with license assignment and group membership in one pass
- [ ] **Stale account report** — accounts with no sign-in activity past a threshold, the input to any real access review
- [ ] **Offshore engineer onboarding helper** — the direct follow-up to the [AppLocker isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md): script the computer group membership add *and* verify exclusion from the standard fleet policy, so the two-step boundary can't be half-completed by hand

---

## Power Automate

- [ ] Ticket intake routing based on request category
- [ ] Onboarding task checklist generation and assignment across IT and HR-adjacent systems
- [ ] Approval workflow for access requests requiring sign-off

---

## Standards I'm Holding Myself To

Automation in an environment governed by HIPAA has a higher bar than "it works." Every script published here needs to meet these before it goes in:

1. **No hardcoded secrets, ever.** Credentials come from a secret store or interactive auth, never from the file.
2. **Read-only by default; destructive actions gated.** Anything that modifies or deletes supports `-WhatIf` and confirms before acting.
3. **Idempotent where possible.** Running it twice should not do the thing twice.
4. **Logs what it did.** An automation you can't audit after the fact is a liability in a compliance-governed environment.
5. **Sanitized before commit.** No tenant IDs, no real hostnames, no internal URLs, no sample data drawn from real users.
