# Microsoft 365 Administration

Tenant administration, Exchange Online, and Entra ID work performed in a HIPAA-regulated healthcare environment of roughly 300 endpoints.

Examples below are generalized. No requester names, email addresses, or organization-identifying detail are included, in line with employer data-handling policy.

---

## Exchange Online & Mail Flow

- Distribution list creation, membership management, and troubleshooting delivery issues
- Shared mailbox provisioning and delegation configuration (full access vs. send-as vs. send-on-behalf, and why the distinction matters to end users who don't know it exists)
- Mailbox permission troubleshooting where the reported symptom ("I can't see the calendar") and the actual cause (delegation scope) didn't match

## Entra ID / Identity

- Multi-factor authentication enrollment and re-enrollment, including recovery for users who lost enrolled devices
- Password reset and account lockout resolution following identity-verification procedure
- Group membership management for application access
- Sign-in troubleshooting: distinguishing a credential problem from a conditional access block from a licensing gap, which are three very different fixes for one identical user-facing error message

## Teams & Collaboration

- Teams provisioning, channel structure, and access troubleshooting
- Teams calling and meeting issues: audio/video device diagnostics, client vs. VDI-specific failure modes
- OneDrive and SharePoint sync troubleshooting, including permission-inheritance issues on shared document libraries

## Licensing & Provisioning

- License assignment as part of new-hire provisioning workflows
- Coordinating application access for role changes, where the license and the group membership and the application-side account all have to line up

---

## Roadmap

- [ ] Exchange Online PowerShell: bulk reporting and permission audit scripts
- [ ] Conditional Access policy design lab
- [ ] Microsoft Purview and retention policy fundamentals (relevant to HIPAA retention requirements)
