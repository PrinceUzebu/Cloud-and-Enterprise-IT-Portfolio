# Azure Labs

Hands-on Azure environment builds, documented as I complete them. This section builds directly on AZ-104 material using real deployed resources rather than exam-only labs.

**Status:** 🔄 Actively building. Labs are added here once they're actually built and broken and fixed — not when they're planned.

---

## Why This Section Exists Separately From Home-Labs

[Home-Labs](../Home-Labs/) is general infrastructure practice — networking, virtualization, self-hosted tooling. This section is specifically Azure, because that's the platform I'm targeting professionally and the depth needs to be different. A recruiter looking for AZ-104-backed practical skill should be able to find it in one place.

---

## Planned Labs

- [ ] **Resource groups + tagging strategy** for a small multi-environment setup (dev/test/prod), including a naming convention doc — the boring part that matters most at scale
- [ ] **VNet peering and NSG rule design** — including deliberately breaking connectivity and diagnosing it with Network Watcher rather than guessing
- [ ] **Hybrid identity lab** (Entra Connect / cloud sync) — directly relevant to the [IAM work](../Experience-Journal/IAM/) in this repo
- [ ] **Conditional Access policy simulation** with a break-glass account, and what happens when you lock yourself out
- [ ] **Cost Management + budget alerting** — because the fastest way to learn Azure cost behavior is to get an alert you didn't expect
- [ ] **Azure Virtual Desktop build** — relevant to the [AppLocker isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md), where I worked with an AVD endpoint from the policy side but didn't build the host pool myself

---

## Format For Each Lab

To keep these useful rather than screenshot dumps, each lab write-up will cover:

1. **What I was trying to learn** — the specific question, not "learn networking"
2. **What I built** — architecture and configuration
3. **What broke** — including the mistakes, because that's where the learning is
4. **What I'd do differently** — and what this changes about how I'd design it in production
