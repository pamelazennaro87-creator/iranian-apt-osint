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
- Infrastructure & hosting pattern analysis
- Cross-references to primary research (Mandiant, Microsoft, ESET, Unit 42, Group-IB, Semperis, etc.)

**This is a defensive / research repository.** No malware samples or operational tooling are hosted.

---

## Main Groups Tracked

| Group | Common Aliases | Likely Affiliation | Primary Focus | Profile Status |
|-------|----------------|--------------------|---------------|----------------|
| **APT33** | Elfin, Peach Sandstorm, Magnallium | IRGC | Energy, aerospace, defense | Initial |
| **APT34** | OilRig, Helix Kitten, Hazel Sandstorm | MOIS | Espionage (gov, finance, energy) | Initial |
| **APT35** | Charming Kitten, Phosphorus, Mint Sandstorm | IRGC | Credential phishing, dissidents, journalists | Initial |
| **MuddyWater** | Static Kitten, Seedworm, Mango Sandstorm | MOIS | Espionage, telecom, government | Initial |
| **Prince of Persia** | Infy | Suspected state-linked | Dissidents + Western targets | **Detailed (2026 infra)** |
| **Tortoiseshell** | UNC1549, Nimbus Manticore | IRGC | Supply-chain, IT providers | Overview |
| **CyberAv3ngers** | — | IRGC-CEC | ICS/OT | Overview |
| **APT39** | Chafer | MOIS | Telecom, travel | Overview |
| **Fox Kitten** | Pioneer Kitten | IRGC | Initial access brokerage | Overview |

Additional clusters tracked in `groups/others.md`.

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
│   ├── prince-of-persia.md
│   └── others.md
├── infrastructure/
│   └── notes.md              # Hosting patterns & geolocation observations
├── iocs/
│   ├── README.md
│   └── public-examples.md    # Curated, sourced public indicators
└── (campaigns / ttp / sources planned)
```

---

## Notable Existing Public Resources

- [KittenBusters/CharmingKitten](https://github.com/KittenBusters/CharmingKitten) — Major 2025 leak
- [misterch0c/APT34](https://github.com/misterch0c/APT34) — Classic OilRig leak
- Semperis Research on Prince of Persia (Oct 2026) — US-hosted C2 discovery
- Vendor reporting: Mandiant, Microsoft, ESET, Unit 42, Group-IB

---

## Methodology

See [`methodology.md`](methodology.md). Core rules:

1. Primary sources preferred
2. Explicit confidence levels
3. Public IOCs only + full attribution
4. Temporal context required
5. No unverified claims presented as fact

---

## Current Status (2026-11-02)

✅ Core structure and methodology  
✅ Profiles: APT33, APT34, APT35, MuddyWater, **Prince of Persia (detailed)**  
✅ Infrastructure & hosting pattern notes  
✅ Curated public IOC examples with sources  
✅ Overview of remaining clusters  

**Next natural steps:**
- Expand APT35 and MuddyWater with campaign timelines
- Add more high-confidence public IOCs (group-by-group)
- Begin MITRE ATT&CK mapping
- Document operational overlaps (e.g. MuddyWater ↔ OilRig/Lyceum)

---

*Independent OSINT research. Defensive use only.*
