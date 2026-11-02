# Campaign Overview & Notable Activity (2024–2026)

This file provides a high-level index of publicly reported Iranian-linked cyber activity. It is intended as a research and investigative reference. All entries are based on open-source reporting.

---

## Key Themes (2024–2026)

- Continued heavy focus on **Israel** and broader Middle East targets across multiple groups.
- Increased use of **legitimate tools** (RMM software, cloud services, satellite internet).
- Documented cases of **operational overlap** between clusters (particularly MuddyWater and OilRig subgroups).
- Persistent credential phishing and social engineering (especially Charming Kitten / APT35).
- Destructive and ICS-oriented activity remains present but often accompanied by exaggerated public claims (CyberAv3ngers).
- Notable infrastructure shifts, including rare use of US-based shared hosting (Prince of Persia, 2026).

---

## Notable Campaigns & Activity Windows

### MuddyWater

| Period | Activity Summary | Primary Targets | Notes / Source Type |
|--------|------------------|-----------------|---------------------|
| Sep 2024 – Mar 2025 | Multi-sector campaign ("Snakes by the riverbank" – ESET) | Israel (engineering, local gov, manufacturing, universities, utilities), 1 Egypt | Custom tools including MuddyViper / Fooder; operational overlap with Lyceum (OilRig subgroup) observed |
| Oct 2025 | Phoenix v4 wave | 100+ government / critical infrastructure entities (MENA) | Compromised mailboxes used for distribution |
| Aug 2025 – Feb 2026 | Four-wave campaign against energy & maritime | Middle East energy/maritime company | Unit 42 (Boggy Serpens assessment); tools included Phoenix, GhostBackDoor, Nuso, Rust-based variants |
| Late 2025 – early 2026 | Starlink C2 experimentation | Various | Reported use of commercial satellite internet for command and control |

### APT35 / Charming Kitten

| Period | Activity Summary | Primary Targets | Notes |
|--------|------------------|-----------------|-------|
| Ongoing (multi-year) | Credential phishing & social engineering | Dissidents, journalists, academics, policy researchers, government | Core persistent activity |
| 2025 | KittenBusters leak | Internal operational exposure | Major public exposure of infrastructure, tooling and some operator-related material |
| 2025 | GenAI-assisted lures (Agent Serpens reporting) | Research / policy targets | Unit 42 observed use of generative AI in lure creation (e.g. RAND-themed) |

### APT34 / OilRig

| Period | Activity Summary | Primary Targets | Notes |
|--------|------------------|-----------------|-------|
| 2024–2025 | Continued espionage + staging infrastructure | Gulf states, energy, government | Dormant staging infrastructure observed; cloud abuse increasing |
| 2024 | Privilege escalation activity (CVE-2024-30088 reported in some campaigns) | UAE / Gulf | Public reporting linked kernel privilege escalation use |

### Prince of Persia

| Period | Activity Summary | Notes |
|--------|------------------|-------|
| Early 2026 | Infrastructure disruption after research publication | Rapid C2 turnover following SafeBreach reporting |
| Mid–late 2026 | Shift to US shared hosting for Tornado C2 | First documented US-based C2 in ~10 years (Semperis); Namecheap shared hosting used for blending |

### CyberAv3ngers

| Period | Activity Summary | Notes |
|--------|------------------|-------|
| 2023–2026 | ICS/OT targeting (Unitronics and similar) | Public claims often exceed confirmed technical impact; focus on internet-exposed industrial controllers |

---

## Investigative Value Notes

For law enforcement and defensive intelligence purposes, the highest-value public signals currently include:

1. **Operational overlaps** between MuddyWater and OilRig/Lyceum (possible initial access sharing).
2. **Infrastructure reuse patterns** and rare shifts (e.g. Prince of Persia US hosting).
3. **Tooling families** that persist across campaigns (Phoenix lineage, Tornado, PowerLess-related, etc.).
4. **Targeting consistency** against specific sectors and communities (dissidents, energy, telecom, Israeli entities).
5. **Abuse of legitimate services** (RMM, cloud, satellite) that can generate pivot points in investigations.

This index will be expanded as additional high-confidence public reporting becomes available.
