# Iranian APT OSINT

**Evidence-first OSINT investigation into Iranian state-aligned cyber threat actors (IRGC / MOIS).**

Claims are tested, not collected.  
Preserve the fingerprint, not the stolen payload.

This repository is structured to be useful for defensive intelligence, detection engineering, and investigative reference. All material is drawn from public sources only.

---

## Scope

- Group profiles with attribution confidence levels
- Campaign timelines (2024–2026 focus)
- Documented operational overlaps between clusters
- Public infrastructure and hosting patterns
- Curated public IOCs with full source attribution
- Investigative notes oriented toward durable signals (tooling, overlaps, behavioral patterns)

**No malware samples. No non-public indicators. Defensive / research use only.**

---

## Main Groups Tracked

| Group | Affiliation | Focus | Profile |
|-------|-------------|-------|---------|
| **APT33** | IRGC | Energy, aerospace, defense | Initial |
| **APT34 / OilRig** | MOIS | Long-dwell espionage | Initial |
| **APT35 / Charming Kitten** | IRGC | Credential phishing, dissidents, journalists | Initial |
| **MuddyWater** | MOIS | Espionage + possible access brokerage | **Expanded** |
| **Prince of Persia** | Suspected state-linked | Dissidents + Western targets | **Detailed (2026 infra)** |
| Others (Tortoiseshell, CyberAv3ngers, APT39, Fox Kitten, Agrius, Void Manticore…) | Mixed | Various | Overview |

---

## Repository Structure

```
iranian-apt-osint/
├── README.md
├── methodology.md
├── groups/                    # Individual actor profiles
├── campaigns/
│   └── overview.md            # 2024–2026 activity index
├── analysis/
│   └── operational-overlaps.md  # Documented connections between clusters
├── infrastructure/
│   └── notes.md               # Hosting & geolocation patterns
└── iocs/
    ├── README.md
    └── public-examples.md     # Curated, sourced indicators
```

---

## Highest-Value Content for Investigators

1. **Operational overlaps** (`analysis/operational-overlaps.md`) — especially MuddyWater ↔ OilRig/Lyceum access-sharing indicators.
2. **Campaign index** (`campaigns/overview.md`) — temporal windows and targeting patterns.
3. **MuddyWater expanded profile** — RMM abuse as hunting signal, victim-overlap notes, tooling evolution.
4. **Prince of Persia 2026 infrastructure shift** — rare US shared-hosting C2 case.
5. **Infrastructure patterns** — registrar preferences, blending techniques, satellite C2 experimentation.

These elements prioritize durable investigative signals over short-lived IOCs.

---

## Methodology

See [`methodology.md`](methodology.md).

Core rules: primary sources preferred · explicit confidence levels · public IOCs only · temporal context required · no unverified claims presented as fact.

---

## Current Status (2026-11-02)

✅ Methodology and structure  
✅ Core + expanded group profiles  
✅ Campaign activity index (2024–2026)  
✅ Operational overlaps analysis  
✅ Infrastructure / hosting notes  
✅ Curated public IOC examples  

**Continuing work:** deeper campaign timelines, additional high-confidence IOCs, MITRE mapping, further overlap research.

---

*Independent OSINT research. Intended for defensive and investigative reference.*
