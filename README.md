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

| Group | Common Aliases | Likely Affiliation | Primary Focus |
|-------|----------------|--------------------|---------------|
| **APT33** | Elfin, Peach Sandstorm, Magnallium, Refined Kitten | IRGC | Energy, aerospace, defense |
| **APT34** | OilRig, Helix Kitten, Hazel Sandstorm, Crambus | MOIS | Espionage (gov, finance, energy) |
| **APT35** | Charming Kitten, Phosphorus, Mint Sandstorm, Magic Hound | IRGC | Credential phishing, dissidents, journalists, academics |
| **MuddyWater** | Static Kitten, TEMP.Zagros, Seedworm | MOIS | Espionage, telecom, government |
| **Tortoiseshell** | UNC1549, Mirage Kitten, Nimbus Manticore | IRGC | Supply-chain, IT service providers |
| **Prince of Persia** | Infy | Suspected state-linked | Dissidents + Western targets |
| **CyberAv3ngers** | — | IRGC-CEC | Destructive / ICS-oriented |
| **APT39** | Chafer, Remexi | MOIS | Telecom, travel, government |
| **Fox Kitten** | Pioneer Kitten, Parisite | IRGC | Initial access brokerage |

---

## Repository Structure

```
iranian-apt-osint/
├── README.md
├── methodology.md              # How we evaluate sources and attribution
├── groups/                     # Individual group profiles
│   ├── apt33-elfin.md
│   ├── apt34-oilrig.md
│   ├── apt35-charming-kitten.md
│   ├── muddywater.md
│   ├── tortoiseshell.md
│   ├── prince-of-persia.md
│   └── others.md
├── campaigns/                  # Notable operations with timelines
├── iocs/                       # Public IOCs only (domains, IPs, hashes)
│   ├── domains.txt
│   ├── ips.txt
│   └── hashes.txt
├── ttp/
│   └── mitre-mapping.md
└── sources/
    └── bibliography.md
```

---

## Notable Existing Public Resources

Before contributing or expanding this repo, review these high-value public sources:

- [KittenBusters/CharmingKitten](https://github.com/KittenBusters/CharmingKitten) — Major 2025 leak exposure of Charming Kitten / IRGC-IO activity
- [misterch0c/APT34](https://github.com/misterch0c/APT34) — Classic OilRig / APT34 leak material
- Vendor reports: Mandiant, Microsoft Threat Intelligence, ESET, Palo Alto Unit 42, Group-IB, Recorded Future

This repository aims to synthesize and maintain a clean, continuously updated evidence graph rather than duplicate existing leaks.

---

## Methodology Principles

1. **Source hierarchy** — Prefer primary technical reports and official advisories over secondary news.
2. **Attribution confidence** — Explicitly state confidence level (High / Medium / Low) and the evidence supporting it.
3. **No unverified claims** — Rumors and single-source allegations are flagged as such.
4. **Public IOCs only** — Only indicators already published by reputable researchers or governments.
5. **Temporal clarity** — Every major claim includes approximate date or campaign window.

---

## Status

🚧 **Under active construction** — Initial structure created 2026-11-02.

Next steps:
- [ ] Populate group profiles with current public knowledge
- [ ] Build initial public IOC lists
- [ ] Create MITRE ATT&CK overview
- [ ] Document major 2024–2026 campaigns

---

*Maintained as part of independent OSINT research.*
