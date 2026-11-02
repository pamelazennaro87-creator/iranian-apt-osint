# Prince of Persia (Infy)

**Also known as:** Infy, Prince of Persia

**Likely affiliation:** Suspected Iranian state-linked (long-running activity against dissidents and Western targets)  
**Confidence:** Medium-High (consistent long-term tracking by multiple researchers)  
**First observed:** ~2010–2016 (public reporting from Unit 42 in 2016; activity traced earlier)  
**Primary motivation:** Espionage and surveillance, with strong focus on Iranian dissidents and selected Western targets

---

## Overview

Prince of Persia is a long-running Iranian-linked threat actor that has operated for nearly two decades. Unlike the more widely tracked IRGC/MOIS clusters (APT33/34/35, MuddyWater), it has maintained a relatively low public profile while consistently targeting Iranian opposition figures and, to a lesser extent, organizations in the United States, Europe and the Middle East.

The group is known for custom malware families including **Foudre**, **Tonnerre**, and the more recent **Tornado** (first- and second-stage).

---

## Targeting Profile

- Iranian dissidents and opposition figures (primary)
- Public and private sector organizations in the US, Europe and Middle East
- Occasional broader targeting aligned with Iranian state interests

---

## Notable 2026 Developments (Public Reporting)

According to Semperis research published in October 2026:

- After a period of reduced visibility, the group shifted C2 strategy.
- For the first time in approximately a decade, a Tornado second-stage C2 server was observed hosted on **US shared hosting** (Namecheap infrastructure).
- Documented C2 IP (publicly reported by Semperis): `68.65.122.203` (AS22612, Namecheap), active from approximately July 2026.
- Additional related infrastructure was observed behind Cloudflare and in other ranges.
- The group has also used Telegram API channels and domain-generation techniques.

This US-based hosting choice is notable because shared hosting blends malicious infrastructure among thousands of legitimate domains, increasing detection difficulty.

---

## Malware Families (Public)

- **Foudre** — First-stage loader
- **Tonnerre** — Second-stage with surveillance capabilities
- **Tornado** — More recent family (first- and second-stage variants), with file-stealing and Telegram C2 options

---

## Key Public Resources

- Semperis Research — “Prince of Persia: A Threat Group Hiding in Plain Sight” (October 2026)
- Earlier Unit 42 and independent researcher tracking
- SafeBreach analysis (early 2026) that appears to have triggered infrastructure changes

---

## Status in this repository

- [x] Initial profile
- [x] 2026 infrastructure notes (public)
- [ ] Full historical timeline
- [ ] Expanded public IOC collection
- [ ] Comparison with other long-running Iranian clusters

*Last updated: 2026-11-02*
