# APT35 — Charming Kitten

**Also known as:** Phosphorus, Mint Sandstorm (Microsoft), Magic Hound (MITRE), NewsBeef, Ajax Security Team, TA453, ITG18, Educated Manticore, Ballistic Bobcat

**Likely affiliation:** Islamic Revolutionary Guard Corps (IRGC) — specifically linked by multiple researchers to IRGC Intelligence Organization elements  
**Confidence:** High (multiple independent high-quality sources + 2025 leak material)

**First observed:** ~2013–2014  
**Primary motivation:** Cyber espionage, credential theft, surveillance of dissidents, journalists, academics, and policy targets of interest to the Iranian government.

---

## Overview

Charming Kitten is one of the longest-running and most persistent Iranian threat actors focused on **human intelligence collection via technical means**. Unlike groups that specialize in destructive operations or broad infrastructure attacks, APT35 is primarily known for highly targeted social engineering and credential phishing campaigns.

The group has repeatedly demonstrated patience, persona development, and the ability to maintain long-term access to high-value personal accounts.

---

## Targeting Profile

- Iranian dissidents and opposition figures (domestic and diaspora)
- Journalists and media organizations covering Iran
- Academics and think-tank researchers focused on Iran, Middle East policy, or nuclear issues
- Government and diplomatic personnel (especially Middle East, US, Europe)
- Civil society and human rights organizations

Geographic focus has historically centered on the Middle East, with consistent operations against targets in the United States, United Kingdom, and broader Europe.

---

## Notable Characteristics

- Heavy reliance on **spear-phishing** and fake personas (journalists, conference organizers, recruiters, romantic interest)
- Frequent use of credential harvesting pages that closely mimic legitimate services (Google, Microsoft, Yahoo, etc.)
- Willingness to engage in prolonged social engineering conversations before delivering a payload or link
- Occasional use of watering-hole style compromises and opportunistic exploitation
- Documented interest in mobile devices and messaging applications in some campaigns

---

## Key Public Resources

- **KittenBusters/CharmingKitten** (GitHub, 2025) — Major leak exposure containing operational logs, malware, and internal material linked to IRGC-IO activity. High-value primary source.
- Microsoft Threat Intelligence reporting on Mint Sandstorm / Phosphorus
- Mandiant / Google TAG reporting on APT35 / APT42 overlaps
- ClearSky, Certfa, and other specialized Iran-focused researchers

---

## Notes on Naming & Clustering

Vendor naming for this activity cluster is particularly messy. Some researchers treat APT42 as a distinct but overlapping cluster; others see significant continuity. This repository currently tracks the core Charming Kitten / APT35 / Phosphorus / Mint Sandstorm activity under this profile and will note significant divergences where evidence supports them.

---

## Status in this repository

- [x] Initial profile created
- [ ] Detailed campaign timeline
- [ ] Public IOC collection
- [ ] MITRE ATT&CK mapping specific to this group
- [ ] Cross-reference with 2025 leak material

*Last updated: 2026-11-02*
