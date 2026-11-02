# APT34 — OilRig

**Also known as:** Helix Kitten, Hazel Sandstorm, Earth Simnavaz, EUROPIUM, Crambus, Cobalt Gypsy, TA452

**Likely affiliation:** Ministry of Intelligence and Security (MOIS) — High confidence  
**First observed:** ~2014  
**Primary motivation:** Long-term cyber espionage

---

## Overview

OilRig is one of Iran’s most persistent and technically capable espionage actors. It specializes in long-dwell operations against government, energy, telecommunications and financial targets, with a strong historical focus on the Middle East (particularly Gulf states) and selective targeting beyond the region.

The group is known for custom tooling, DNS tunneling, web shells, and the abuse of trusted relationships / supply-chain vectors.

---

## Targeting Profile

- Government and diplomatic entities (especially Middle East)
- Energy and oil & gas sector
- Telecommunications
- Financial institutions
- Occasional targeting in Europe and North America

---

## Notable TTPs (High-level)

- Spear-phishing and strategic web compromises
- Custom web shells (TwoFace and variants)
- DNS tunneling for C2 and data exfiltration
- Credential harvesting and lateral movement via stolen accounts
- Abuse of Microsoft services (Exchange, OneDrive, Azure) in later campaigns
- Privilege escalation via known vulnerabilities (including kernel-level in some 2024 activity)

---

## Infrastructure Notes (Public)

OilRig has historically used a mix of:
- Bulletproof / low-regulation hosting
- Compromised legitimate infrastructure
- Domains that mimic academic, government or technology organizations
- Periodic reuse of infrastructure patterns (SSH fingerprints, port behaviors, naming conventions)

Researchers have repeatedly observed staging infrastructure that remains dormant for months before activation — a characteristic of careful operational security.

---

## Key Public Resources

- Classic 2019 APT34 leak material (misterch0c/APT34)
- Microsoft, Mandiant, Check Point, Unit 42 and ESET reporting
- Multiple CISA and regional advisories over the years

---

## Status in this repository

- [x] Initial profile
- [ ] Detailed campaign timeline (2014–2026)
- [ ] Public IOC collection (domains / IPs / hashes with sources)
- [ ] MITRE ATT&CK mapping
- [ ] Infrastructure evolution analysis

*Last updated: 2026-11-02*
