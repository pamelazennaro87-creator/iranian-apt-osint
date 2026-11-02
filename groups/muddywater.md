# MuddyWater

**Also known as:** Static Kitten, Seedworm, TEMP.Zagros, Mango Sandstorm, MERCURY, TA450, Earth Vetala

**Likely affiliation:** Ministry of Intelligence and Security (MOIS) — **High confidence** (explicitly stated in joint CISA/FBI/NCSC advisories)  
**First observed:** ~2017  
**Primary motivation:** Espionage and intelligence collection; occasional destructive or ransomware follow-on

---

## Overview

MuddyWater is a persistent MOIS-linked actor focused on government, telecommunications, defense and critical infrastructure. It is one of the more operationally active Iranian clusters in the 2024–2026 period. The group is pragmatic: it combines custom malware with heavy abuse of legitimate remote management tools and has shown willingness to act as an initial access provider for other Iran-aligned actors.

---

## Targeting Profile

**Primary:**
- Government and local administration
- Telecommunications
- Energy and maritime sectors
- Defense and critical infrastructure

**Geographic focus:** Strong concentration on Israel and the broader Middle East / North Africa. Documented activity also in Europe, Asia and North America.

---

## Notable Campaign Activity (Public)

| Period | Summary | Key Characteristics |
|--------|---------|---------------------|
| Sep 2024 – Mar 2025 | Multi-sector Israeli campaign (ESET: “Snakes by the riverbank”) | Engineering, local government, manufacturing, universities, utilities; one Egyptian technology target. Introduction/use of MuddyViper and Fooder (Snake-game masquerade). |
| Early 2025 | Overlap with Lyceum (OilRig subgroup) | Same victim environment accessed by both actors (utilities sector case). Supports initial-access-broker assessment. |
| Oct 2025 | Phoenix v4 wave | Compromised mailboxes used to target 100+ government and critical infrastructure entities across MENA. |
| Aug 2025 – Feb 2026 | Four-wave energy & maritime campaign (Unit 42) | Sequential waves with evolving lures and tools (Phoenix, GhostBackDoor, Nuso, Rust-based variants). |
| Late 2025 – early 2026 | Starlink C2 experimentation | Reported use of commercial satellite internet for command and control. |

---

## TTPs of Investigative Interest

- **Initial access:** Spear-phishing, often from already-compromised mailboxes; macro-enabled documents; occasional exploitation of public-facing applications.
- **Persistence & control:** Heavy and distinctive use of legitimate RMM tools (ConnectWise, Syncro, Atera, PDQ and similar). This is one of the more reliable behavioral signals.
- **Tooling evolution:** Historical PowerShell emphasis → increasing use of compiled custom backdoors and Rust-based tools in 2025–2026.
- **Credential access & lateral movement:** Standard post-exploitation credential theft and movement.
- **Potential access sharing:** Documented temporal and victim overlap with OilRig/Lyceum activity.

---

## Infrastructure Characteristics (Public)

- Rapid domain turnover; many short-lived domains.
- Frequent use of NameCheap and similar registrars; Hosterdaddy appears in some reporting.
- Cloudflare and CDN usage for obfuscation.
- Experimentation with non-traditional C2 channels (Starlink).
- Infrastructure is generally low-dwell; static IOC value decays quickly.

---

## Investigative Notes (for LE / Defensive Use)

1. **RMM abuse** is a high-value hunting signal. Presence of unexpected remote management software in government, telecom or energy environments warrants scrutiny.
2. **Victim overlap** with OilRig/Lyceum activity should be treated as a potential coordination or access-sharing indicator rather than coincidence.
3. Compromised mailboxes used for distribution create opportunities for email-header and account-takeover analysis.
4. Tooling families (Phoenix lineage, MuddyViper, newer Rust variants) provide more durable detection opportunities than individual IPs or domains.
5. Joint CISA/FBI/NCSC advisories remain the strongest public attribution baseline.

---

## Key Public Resources

- CISA / FBI / NCSC joint advisories (AA22-055A and related)
- ESET: “MuddyWater: Snakes by the riverbank” (Dec 2025)
- Unit 42 Boggy Serpens / related 2026 assessments
- Symantec / Broadcom Seedworm reporting

---

## Status in this repository

- [x] Expanded profile with campaign windows
- [x] Investigative notes
- [x] Link to operational overlap analysis
- [ ] Deeper public IOC curation
- [ ] Formal MITRE ATT&CK mapping

*Last updated: 2026-11-02*
