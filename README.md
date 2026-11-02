# Iranian APT OSINT

**Evidence-first OSINT investigation into Iranian state-aligned cyber threat actors (IRGC / MOIS).**

Claims are tested, not collected.  
Preserve the fingerprint, not the stolen payload.

---

## Scope

This repository tracks Iranian Advanced Persistent Threat (APT) groups and related cyber operations with a strict evidence-first approach:

- Public source genealogy
- Attribution confidence levels
- Campaign timelines
- Public Indicators of Compromise (IOCs)
- MITRE ATT&CK mapping
- Cross-references to primary research (Mandiant, Microsoft, ESET, Unit 42, Group-IB, etc.)

**This is a defensive / research repository.** No malware samples or operational tooling are hosted.

---

## Main Groups Tracked

| Group | Common Aliases | Likely Affiliation | Primary Focus | Profile Status |
|-------|----------------|--------------------|---------------|----------------|
| **APT33** | Elfin, Peach Sandstorm, Magnallium, Refined Kitten | IRGC | Energy, aerospace, defense | Initial |
| **APT34** | OilRig, Helix Kitten, Hazel Sandstorm, Crambus | MOIS | Espionage (gov, finance, energy) | Initial |
| **APT35** | Charming Kitten, Phosphorus, Mint Sandstorm, Magic Hound | IRGC | Credential phishing, dissidents, journalists, academics | Initial |
| **MuddyWater** | Static Kitten, TEMP.Zagros, Seedworm, Mango Sandstorm | MOIS | Espionage, telecom, government | Initial |
| **Tortoiseshell** | UNC1549, Mirage Kitten, Nimbus Manticore | IRGC | Supply-chain, IT service providers | Overview |
| **Prince of Persia** | Infy | Suspected state-linked | Dissidents + Western targets | Overview |
| **CyberAv3ngers** | — | IRGC-CEC | Destructive / ICS-oriented | Overview |
| **APT39** | Chafer, Remexi | MOIS | Telecom, travel, government | Overview |
| **Fox Kitten** | Pioneer Kitten, Parisite | IRGC | Initial access brokerage | Overview |

Additional clusters (Agrius, Void Manticore, Cotton Sandstorm, etc.) are tracked in `groups/others.md`.

---

## Repository Structure

```
iranian-apt-osint/
├── README.md
├── methodology.md
├── groups/
│   ├── apt33-elfin.md
│   ├── apt34-oilrig.md
│   ├── apt35-charming-kitten.md
│   ├── muddywater.md
│   └── others.md
├── iocs/
│   └── README.md          # Rules + collection status
├── campaigns/             # (planned)
├── ttp/                   # (planned)
└── sources/               # (planned)
```

---

## Notable Existing Public Resources

- [KittenBusters/CharmingKitten](https://github.com/KittenBusters/CharmingKitten) — Major 2025 leak exposure of Charming Kitten / IRGC-IO activity
- [misterch0c/APT34](https://github.com/misterch0c/APT34) — Classic OilRig / APT34 leak material
- Vendor reports: Mandiant, Microsoft Threat Intelligence, ESET, Palo Alto Unit 42, Group-IB, Recorded Future, Semperis (Prince of Persia 2026)

---

## Methodology Principles

1. **Source hierarchy** — Prefer primary technical reports and official advisories over secondary news.
2. **Attribution confidence** — Explicitly state confidence level (High / Medium / Low) and the evidence supporting it.
3. **No unverified claims** — Rumors and single-source allegations are flagged as such.
4. **Public IOCs only** — Only indicators already published by reputable researchers or governments.
5. **Temporal clarity** — Every major claim includes approximate date or campaign window.

Full details in [`methodology.md`](methodology.md).

---

## Current Status (2026-11-02)

✅ Repository created and structured  
✅ Methodology documented  
✅ Core profiles added: APT33, APT34, APT35, MuddyWater  
✅ Overview of additional clusters  
✅ IOC collection rules established  

**Next priorities:**
1. Populate public IOCs for APT35 (richest data) and MuddyWater
2. Expand APT34 and APT33 profiles with campaign timelines
3. Add MITRE ATT&CK mapping
4. Begin infrastructure / geolocation notes (public hosting patterns only)

---

*Maintained as part of independent OSINT research. Defensive use only.*
