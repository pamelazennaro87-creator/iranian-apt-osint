# Methodology

This repository is an **evidence-first OSINT dossier**.  
It organises public reporting so investigators and defenders can orient faster — it does not create non-public intelligence.

---

## Core Principles

1. **Claims must be sourced** — primary or high-quality secondary sources; no unsupported assertions presented as fact.  
2. **Attribution is never assumed** — confidence levels are stated; cluster boundaries are documented when fluid.  
3. **Public indicators only** — no non-public IOCs, no malware samples, no operational access data.  
4. **Temporal context required** — significant claims are tied to time windows (especially 2024–2026).  
5. **No invented links** — overlaps between clusters are recorded only when publicly documented; hypotheses are labelled as such.  
6. **Durable signals over ephemeral IOCs** — behavioural patterns (RMM abuse, edge exploitation, OT exposure, non-traditional C2) are prioritised for investigative value.

---

## Source Hierarchy

| Priority | Source type | Examples |
|----------|-------------|----------|
| 1 (Highest) | Official government advisories & actions | CISA, FBI, NSA, NCSC, joint CSA, Treasury |
| 2 | Primary technical research (major vendors) | Mandiant, Microsoft, ESET, Unit 42, Semperis, CrowdStrike |
| 3 | High-quality independent technical analysis | Verifiable researcher work with artefacts |
| 4 | Reputable secondary CTI / specialist reporting | Established CTI shops, specialised outlets |
| 5 (Lowest) | News aggregation / social claims | Leads only — never sole evidence |

Hacktivist or persona claims (e.g. Telegram) are treated as **narrative** until supported by independent technical evidence.

---

## Attribution Confidence Levels

| Level | Meaning |
|-------|--------|
| **High** | Multiple independent high-quality sources, strong technical overlap, and/or official attribution |
| **Medium** | Consistent multi-source reporting; some ambiguity in cluster boundaries or sponsorship |
| **Low** | Limited sources, possible mix with other clusters, or inference mainly from targeting/motivation |

Iranian actor naming is fragmented across vendors (APT numbers, Sandstorm names, Kitten names, UNC designations). This repo records aliases and notes uncertainty rather than forcing a single identity.

---

## How investigative material is built

- **Profiles** — sponsorship (as publicly assessed), targeting, TTPs, infrastructure habits, investigative notes  
- **Analysis** — cross-cluster reading, geopolitical correlation, under-emphasised angles, explicit gaps  
- **Checklists** — questions and controls mapped to real public cases (with examples), for IR and hunting  
- **IOC files** — only already-disclosed indicators, with source and context; not presented as complete or current blocklists  

---

## What this repository does *not* do

- Host or distribute malware samples  
- Publish non-public or victim-specific data  
- Assert legal attribution or individual identification  
- Treat vendor marketing language as fact  
- Claim exclusivity over public research by others  

---

## Update policy

| Trigger | Action |
|---------|--------|
| Major new public research or advisory | Profile / analysis update |
| Significant new campaign window | Campaign or timeline entry |
| Conflicting public information | Document both sides with sources and confidence |
| IOC decay or takedown | Note context; do not present stale indicators as live without caveat |

---

## Intended use

**Appropriate:** defensive intelligence, detection engineering, investigative orientation, OSINT training reference, professional portfolio demonstration of method.  

**Not appropriate:** sole basis for legal action, targeting of individuals, or offensive operations.

---

*Independent OSINT research. Public sources only.*
