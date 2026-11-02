# MuddyWater

**Also known as:** Static Kitten, Seedworm, TEMP.Zagros, Mango Sandstorm, MERCURY, TA450, Earth Vetala

**Likely affiliation:** Ministry of Intelligence and Security (MOIS) — **High confidence** (explicitly stated in joint CISA/FBI/NCSC advisories)  
**First observed:** ~2017  
**Primary motivation:** Espionage and intelligence collection; occasional destructive or ransomware follow-on; documented access-sharing behaviour

---

## Overview

MuddyWater is one of the most operationally active and pragmatic MOIS-linked clusters in the 2024–2026 period. It combines custom malware, heavy abuse of legitimate RMM tools, experimentation with non-traditional C2 (including Starlink), and has been observed both overlapping with other Iranian clusters and appearing as a customer of Russian-speaking Malware-as-a-Service platforms.

---

## Targeting Profile

**Primary:** Government and local administration, telecommunications, energy and maritime, defense and critical infrastructure.  
**Geographic focus:** Strong concentration on Israel and broader MENA; documented activity also in Europe, Asia and North America.

---

## Notable Campaign Activity (Public)

| Period | Summary | Key Characteristics |
|--------|---------|---------------------|
| Sep 2024 – Mar 2025 | Multi-sector Israeli campaign (ESET) | MuddyViper, Fooder (Snake-game), RMM abuse; utilities victim later also accessed by Lyceum |
| Early 2025 | Operational overlap with Lyceum (OilRig subgroup) | Same victim environment – supports access-broker / sharing assessment |
| Oct 2025 | Phoenix v4 wave | Compromised mailboxes → 100+ government/CI entities MENA |
| Aug 2025 – Feb 2026 | Four-wave energy & maritime (Unit 42) | Evolving tooling including Rust-based variants |
| Late 2025 – early 2026 | **Starlink C2** | Commercial satellite internet used for command and control |
| 2025+ | Starlink-branded spyware lure | DCHSpy / Earth VPN samples distributed as “Starlink VPN” against Iranian users seeking uncensored access |

---

## TTPs of Highest Investigative Interest

- **RMM as primary foothold and C2** (Atera, ScreenConnect, Syncro, PDQ, SimpleHelp, Level, etc.) — strongest durable behavioural signal.
- **Starlink / satellite C2** (late 2025–early 2026) — changes geolocation assumptions; requires correlation with traditional infrastructure.
- **Dual-use of the Starlink brand** — same cluster uses the technology for its own C2 and weaponises the brand against domestic users.
- **Possible MaaS relationship** — 2026 reporting indicates MuddyWater appeared as customer of a Russian-speaking Malware-as-a-Service platform (code-signing certificates and adjacent infrastructure). This weakens pure “tooling = nationality” attribution.
- **Access sharing** — documented temporal/victim overlap with OilRig/Lyceum.

---

## Infrastructure Characteristics

- Rapid domain turnover; Namecheap and Hosterdaddy frequently observed.
- Cloudflare and CDN usage.
- Experimentation with Starlink as non-terrestrial C2 channel.
- Low-dwell infrastructure; behavioural signals outlast individual IOCs.

---

## Investigative Notes (LE / Defensive)

1. Treat unexpected RMM agents as high-priority identities (inventory tenant IDs).
2. In periods of Iranian internet blackout or high tension, actively hunt for satellite-exit or SpaceX-related C2 patterns linked to known MuddyWater tooling.
3. When analysing MuddyWater samples from 2025–2026, check code-signing certificates against criminal MaaS clusters.
4. Victim overlap with OilRig/Lyceum is a coordination signal, not noise.
5. Starlink-related lures targeting Iranians are a separate but linked activity line useful for persona and intent analysis.

---

## Key Public Resources

- CISA/FBI/NCSC joint advisories (AA22-055A and related)
- ESET “Snakes by the riverbank” (2025)
- Unit 42 Boggy Serpens / 2026 assessments
- MITRE ATT&CK G0069 (explicit satellite internet C2 note)
- Lookout (DCHSpy / Starlink lure)
- 2026 reporting on MaaS customer relationship

---

## Status in this repository

- [x] Expanded campaign timeline
- [x] Starlink C2 and dual-use brand analysis
- [x] MaaS relationship flag
- [x] Access-sharing notes
- [ ] Deeper public IOC and certificate collection

*Last updated: 2026-11-02*
