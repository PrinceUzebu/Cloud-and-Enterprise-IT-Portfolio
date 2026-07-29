# Privileged Access Management

Controlling elevated and outsourced access without grinding the business to a halt. This section covers work where the core problem was *who should be able to do what, for how long, and who decides*.

---

## Work In This Domain

| Work | PAM Concept Demonstrated |
|---|---|
| [Offshore Engineer AppLocker Isolation](../Cloud-Projects/AppLocker-Isolation.md) | Third-party and contractor access scoping. Least privilege enforced at the application-execution layer, not just the network layer |
| [Dynamic Travel Access Provisioning](../Cloud-Projects/Dynamic-Travel-Access-Provisioning.md) | Time-bound elevated access with automatic revocation as the design goal |

---

## Third-Party Access: The Part People Skip

The AppLocker isolation project is fundamentally a PAM problem wearing endpoint-security clothing. A contract engineer needed *enough* access to build software and *no* access to a HIPAA-regulated business environment, and the default fleet configuration granted the second along with the first, because it was written for trusted internal employees.

Three principles came out of that work that I'd apply to any third-party access design:

1. **A procedural boundary is not a boundary.** "The contractor won't access internal systems" is an expectation. An enforced application-control policy is a control. Only one of those survives an audit or a bad actor.
2. **Least privilege has to be decided per category, not per request.** I classified every rule against a single written principle (retain OS/vendor-signed and build tooling, remove business systems and branded tooling) rather than deciding each one on instinct. That's what made the decisions defensible and repeatable.
3. **Some removals aren't yours to make.** Stripping an EDR agent from a machine is a compensating-control decision that belongs with security engineering. Escalating those wasn't indecision, it was scope discipline.

---

## Roadmap

- [ ] Entra ID Privileged Identity Management (PIM) lab: just-in-time role activation with approval workflow
- [ ] Access review cycle design for contractor accounts (who reviews, on what cadence, what triggers revocation)
- [ ] Document offboarding automation for third-party engineers as the pattern gets reused
