# Methodology

## Core Principles

This repository follows an **evidence-first** approach:

1. Claims must be supported by primary or high-quality secondary sources.
2. Attribution is never assumed — confidence levels are always stated.
3. Single-source or low-quality claims are clearly flagged.
4. Only publicly disclosed indicators are collected.
5. Temporal context is required for every significant claim.

---

## Source Hierarchy

| Priority | Source Type | Examples |
|----------|-------------|----------|
| 1 (Highest) | Official government advisories & indictments | CISA, DOJ, NCSC, etc. |
| 2 | Primary technical research from major vendors | Mandiant, Microsoft, ESET, Unit 42, Group-IB, CrowdStrike |
| 3 | High-quality independent researchers / leaks with verifiable material | KittenBusters, major leak analyses |
| 4 | Reputable secondary analysis | Recorded Future, CyberScoop, specialized CTI blogs |
| 5 (Lowest) | News aggregation / unverified social media | Used only for leads, never as sole evidence |

---

## Attribution Confidence Levels

- **High** — Multiple independent high-quality sources, strong technical overlaps (infrastructure, tooling, targeting patterns), or official attribution.
- **Medium** — Consistent reporting across several sources, but some ambiguity in cluster boundaries or sponsorship.
- **Low** — Limited sources, possible overlaps with other clusters, or primarily based on targeting/motivation rather than technical evidence.

When clusters are fluid (common with Iranian actors), we document naming differences and note potential overlaps rather than forcing a single identity.

---

## What We Do Not Do

- Host or distribute malware samples
- Publish non-public IOCs
- Make definitive attributions without supporting evidence
- Treat vendor marketing language as fact

---

## Update Policy

- Major new public research → profile update
- Significant new campaign → new entry under `/campaigns`
- Conflicting information → documented with sources and confidence assessment
