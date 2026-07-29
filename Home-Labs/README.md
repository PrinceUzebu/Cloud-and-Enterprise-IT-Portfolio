# Home Labs

Self-directed learning environments built to go deeper than my day-job scope allows. Non-Azure-specific work lives here — Azure builds are in [Azure-Labs](../Azure-Labs/).

---

## Infrastructure as Code / Terraform

**Status:** 🔄 Starting — new territory, tracked honestly

This is being kicked off through a mentor-guided project transitioning enterprise infrastructure from manual configuration toward Terraform-managed IaC. I'm documenting the learning curve as it actually happens, not retroactively once it looks clean.

Worth noting: Terraform already appeared in the [AppLocker isolation project](../Experience-Journal/Cloud-Projects/AppLocker-Isolation.md) as a build tool I deliberately **retained** in the contractor's allowlist. Understanding it well enough to make that call correctly is different from being able to write it — closing that second gap is the point of this track.

- [ ] Terraform fundamentals: providers, state, and the plan/apply cycle
- [ ] First module: resource group + storage account, written from scratch rather than copied
- [ ] State management: remote backend, and what actually goes wrong when two people apply at once
- [ ] Mentor-led project: initial infrastructure-as-code migration (details added as it progresses)

---

## Networking

- [ ] Virtual network segmentation design and subnet planning
- [ ] Firewall / NSG rule engineering — including least-privilege rule sets and how to audit them
- [ ] DNS fundamentals deep-dive, driven by how often DNS turned out to be the real answer in service desk work
- [ ] VPN and remote access architecture

---

## Virtualization & Self-Hosted Tooling

- [ ] Hypervisor lab for building disposable test environments quickly
- [ ] Windows Server AD lab — useful contrast to the non-domain-joined `WORKGROUP` endpoint in the AppLocker project, where the lack of domain join changed which policy layers applied
- [ ] Self-hosted monitoring stack, to build intuition for what production observability is actually doing

---

## Ground Rules For This Section

No lab gets written up here just for having been followed. Each entry needs a specific question it answered and at least one thing that broke — otherwise it's tutorial output, and this repo is deliberately not that.
