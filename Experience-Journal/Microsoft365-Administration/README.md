# Microsoft 365 Administration

Tenant administration, Exchange Online, and Entra ID work performed in a HIPAA-regulated healthcare environment of roughly 300 endpoints.

Examples below are generalized. No requester names, email addresses, tenant or application identifiers, internal URLs, or organization-identifying detail are included, in line with employer data-handling policy.

---

## Entra ID / Identity

- Multi-factor authentication enrollment and re-enrollment, including recovery for users who lost enrolled devices
- Password reset and account lockout resolution following identity-verification procedure
- Group membership management for application access
- Access suspension and restoration for extended leave, coordinated with HR-adjacent processes
- Sign-in troubleshooting: distinguishing a credential problem from a conditional access block from a licensing gap, which are three very different fixes for one identical user-facing error message

### App Registrations & Consent

The more interesting identity work has come from supporting internally built applications that authenticate against the tenant:

- **Redirect URI configuration on app registrations.** A preview environment for an internal application failed sign-in because its URL was not on the app registration's redirect URI allowlist, surfacing as `AADSTS50011`. Production worked, which is the detail that makes this diagnosable: when one environment authenticates and another doesn't, the difference is almost always registration configuration rather than the application itself
- **Admin consent request lifecycle** for third-party application integrations, including requests that expired before approval. An expired consent request is a decision point rather than a cleanup item, since resubmitting it means re-confirming the integration is still needed and still appropriate
- Working with application owners who don't hold edit rights on the registration, which is the permission model working correctly rather than a problem to route around

## Exchange Online & Mail Flow

- Distribution list creation, membership management, and troubleshooting delivery issues
- Email alias creation and management
- Shared mailbox provisioning and delegation configuration (full access vs. send-as vs. send-on-behalf, and why the distinction matters to end users who don't know it exists)
- Mailbox permission troubleshooting where the reported symptom ("I can't see the calendar") and the actual cause (delegation scope) didn't match

## Teams & Collaboration

- Teams provisioning, channel structure, and access troubleshooting
- Teams calling and meeting issues: audio and video device diagnostics, client vs. VDI-specific failure modes
- OneDrive and SharePoint sync troubleshooting, including permission-inheritance issues on shared document libraries
- Guest and external collaborator access for partner organization staff, including diagnosing whether an account exists to be added at all before troubleshooting the sign-in

## Licensing & Provisioning

- License assignment as part of new-hire provisioning workflows
- Office application deployment for users needing capability their current license or install didn't cover
- Coordinating application access for role changes, where the license and the group membership and the application-side account all have to line up

---

## Roadmap

- [ ] Exchange Online PowerShell: bulk reporting and permission audit scripts
- [ ] Conditional Access policy design lab
- [ ] App registration and enterprise application governance reference
- [ ] Microsoft Purview and retention policy fundamentals (relevant to HIPAA retention requirements)
