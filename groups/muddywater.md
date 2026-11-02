# MuddyWater

**Also known as:** Static Kitten, Seedworm, TEMP.Zagros, Mango Sandstorm, MERCURY, TA450, Earth Vetala

**Likely affiliation:** Ministry of Intelligence and Security (MOIS) — High confidence (explicitly stated in joint CISA/FBI/NCSC advisories)  
**First observed:** ~2017  
**Primary motivation:** Espionage and intelligence collection

---

## Overview

MuddyWater is a workhorse MOIS-linked actor focused on government, telecommunications, defense and critical infrastructure targets, primarily in the Middle East but with documented global reach. The group is known for pragmatic tooling, heavy use of PowerShell, legitimate remote management tools (RMM), and periodic operational overlap with other Iranian clusters (including OilRig subgroups).

In recent years the group has shown increased operational tempo, use of custom backdoors (Phoenix, MuddyViper, etc.), and experimentation with satellite-based C2 (Starlink reported in late 2025 / early 2026).

---

## Targeting Profile

- Government and local administration
- Telecommunications
- Energy and maritime
- Defense and critical infrastructure
- Occasional targeting in Europe, Asia and North America

Strong historical focus on Israel, Gulf states, and broader MENA region.

---

## Notable TTPs (High-level)

- Spear-phishing (including from compromised mailboxes)
- Use of legitimate RMM tools (ConnectWise, Syncro, Atera, PDQ, etc.) for persistence and control
- Custom loaders and backdoors (PowerShell-heavy historically; later shifts toward compiled and Rust-based tools)
- Credential theft and lateral movement
- Occasional ransomware / destructive follow-on activity in some campaigns
- Documented cases of acting as initial access broker for other Iran-aligned actors

---

## Infrastructure Notes (Public)

- Frequent use of NameCheap and similar registrars
- Short-lived domains and rapid infrastructure turnover
- Cloudflare and other CDNs for obfuscation
- Reported use of commercial satellite internet for C2 in 2025–2026
- Occasional reuse of older domains

---

## Key Public Resources

- Joint CISA / FBI / NCSC advisories (especially AA22-055A)
- ESET, Unit 42, Symantec / Broadcom reporting
- Multiple 2025–2026 campaign analyses (Phoenix v4, MuddyViper, maritime/energy waves)

---

## Status in this repository

- [x] Initial profile
- [ ] Detailed campaign timeline
- [ ] Public IOC collection with sources
- [ ] MITRE ATT&CK mapping
- [ ] Analysis of operational overlaps with OilRig / Lyceum

*Last updated: 2026-11-02*
