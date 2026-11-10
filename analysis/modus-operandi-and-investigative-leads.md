# Modus Operandi & Investigative Leads – Shahid Kaveh / CyberAv3ngers

**Scope:** Evidence-first summary of publicly documented TTPs + durable signals useful for investigators and defenders.  
**Sources:** CERT-FR/C4, CISA AA23-335A & AA26-097A, OFAC, OpenAI, industry reporting (Claroty, Tenable, Orion Policy, DomainTools), open biographical data, historical leaks (Lab Dookhtegan / Iran International / Sky News).

> Goal: surface observable patterns and residual OPSEC failures that remain useful for attribution, hunting and disruption — not ephemeral IOCs.

---

## 1. Core Modus Operandi (High Confidence)

Shahid Kaveh operates as an **offensive OT/ICS disruption unit**, not a classic long-dwell espionage cluster.

### Initial Access
- Internet-exposed industrial devices (PLCs, HMIs, refrigeration controllers)
- Default or weak credentials (documented extensively on Unitronics and similar)
- Mass scanning (FOFA and similar tools explicitly noted by French authorities)
- Later evolution: legitimate vendor engineering software (Studio 5000 / FactoryTalk, EcoStruxure, TIA Portal) run from leased overseas VPS to blend with authorized maintenance sessions

### Impact Actions
- Temperature / defrost setting manipulation (France 2026 campaign)
- HMI defacement
- Logic modification or erasure
- Credential changes to lock out operators
- In some cases: deployment of IOCONTROL (MQTT over TLS, DoH)

### Supporting Characteristics
- Persian/Farsi language artefacts in attack infrastructure
- Re-use of previously associated infrastructure
- Public claims via rotating personas (CyberAveng3rs, Soldiers of Solomon, Mr. Soul, Cyber Isnaad Front) + CyberbanNews outlet
- Preference for visible, operationally painful effects over stealthy data theft

---

## 2. Recruitment – What Is Publicly Known (Medium / Low Confidence)

Public information is limited.

- Orion Policy assessment: recruitment is **unlikely** to be open/public. More probable through established IRGC channels, technical universities and pro-regime communities.
- Hamid Reza Lashgarian has documented academic ties to **Imam Hossein University** (IRGC-linked institution) and research activity in electronic warfare.
- Reza Salarvand: public education record at Azad University – South Branch (Tehran), IT Engineering (~2017).
- Broader Iranian cyber ecosystem uses specialised academies (e.g. Ravin Academy – US-sanctioned) that train young operators, some of whom later appear in state-linked activity. Direct pipeline to Shahid Kaveh is not publicly confirmed.

**Investigative note:** Academic and research affiliations of named leadership remain one of the more durable open-source pivots.

---

## 3. Divergent / High-Value Investigative Angles (Publicly Observable)

These are residual signals and under-emphasised patterns that can still yield investigative value:

### A. Infrastructure & Behavioural Fingerprints
- **Engineering software from atypical locations:** Studio 5000 / FactoryTalk / similar tools originating from VPS ranges (notably historical ULTAHOST / AS214036 clusters in public CISA data). This is more durable than any single IP.
- **Port and protocol preferences:** 20256 (Unitronics), 44818, 2222, 102, 502 (Modbus), MQTT 8883.
- **FOFA / similar scanning signatures** combined with subsequent OT targeting.
- Self-signed certificates or specific hostnames on engineering workstations (publicly noted in some Censys-linked analysis of the 185.82.73.x cluster).

### B. Persona & Propaganda Coupling
- Claims often appear shortly after real activity via CyberbanNews or related Telegram channels. Timing correlation between technical indicators and propaganda posts can strengthen attribution.
- Persona domains historically registered via Namecheap with privacy protection (cyberav3ngers.* family).
- **CyberbanNews Telegram strategy (public analysis):** Over 23,000 messages examined across the Farsi channel (active since Feb 2020) and later English channel. The outlet presents itself as a neutral cybersecurity news agency and never names “Shahid Kaveh”, while still referencing operational personas (CyberAv3ngers etc.). This dual-track approach (technical operations + seemingly independent media) is a consistent pattern.

### C. Leadership & Human Residuals
- **Academic pivot (strong residual):** Hamid Reza Lashgarian is publicly linked as assistant professor / researcher at Imam Hossein University (IRGC’s primary military academic institution). Documented paper titles include:
  - Role of UAVs in electronic warfare – integration needs and challenges
  - Bayesian methods to reduce ambiguity in marine target identification
  - Analysing enemy behaviour using Markov models based on electronic warfare observations
- **Family reporting:** Open-source claims of family relationship between Hamid Reza and Mahdi Lashgarian (treat as medium confidence).
- **Historical leaks (high value):** Lab Dookhtegan / Iran International / Sky News material (2020–2021) on Reza Salarvand and **Intelligence Group / Team 13**. The leaked reports examined vulnerabilities in:
  - Ballast water control systems on cargo ships
  - Maritime satellite communications
  - Fuel tank / pump management systems
  - Smart building controls
  - WAGO programmable logic controllers
  These documents remain one of the few detailed public windows into internal targeting priorities.
- **Organizational code (from leaked diagrams):** Shahid Kaveh / Intelligence Team 13 appears under code **360/1**.
- **Rewards for Justice:** Active $10M bounty on Hamid Reza Lashgarian increases the value of any new open-source identification of associates or infrastructure.

### D. Targeting Logic
- Preference for Israeli-made or widely deployed industrial equipment that is left internet-exposed.
- Expansion from water/wastewater → energy → commercial refrigeration shows a consistent focus on physical-process disruption rather than pure IT compromise.
- Reconnaissance against Schneider Electric systems in France (Modbus 502) months before the October 2026 attack is a documented pre-positioning signal.

### E. OPSEC Failures Worth Hunting
1. Re-use of infrastructure across campaigns.
2. Language artefacts (Farsi).
3. Predictable product targeting (Unitronics → Rockwell → multi-vendor).
4. Coupling of technical operations with public claims (and the “independent media” layer of CyberbanNews).
5. Use of AI tools for reconnaissance (OpenAI publicly documented CyberAv3ngers-linked accounts researching ICS, default credentials and scripting).
6. Symbolic domain registrations timed to propaganda milestones.

---

## 4. Practical Hunting Recommendations (Defensive / Investigative)

| Priority | Action |
|----------|--------|
| Highest | Inventory and remove internet exposure of PLCs / refrigeration controllers / HMIs |
| High | Monitor for vendor engineering software connections from non-standard geographies / hosting providers |
| High | Alert on Modbus 502, EtherNet/IP 44818 and related OT ports from external sources |
| Medium | Correlate FOFA-style scanning with subsequent OT access attempts |
| Medium | Track persona domain registrations and CyberbanNews content timing against technical events |
| Medium | Monitor academic output and co-author networks linked to Imam Hossein University electronic-warfare research |
| Ongoing | Re-validate any historical IPs from CISA AA26-097A against current passive DNS before action |

---

## 5. What Remains Missing / High-Value Gaps

- No public full IOC set for the October 2026 French campaign.
- Limited independent confirmation of internal recruitment pipelines specific to Shahid Kaveh.
- Sparse public visibility into the exact relationship between Intelligence Group 13 tasking and operational execution after 2021.
- Few durable human identifiers beyond the three named individuals and their OFAC records.
- No current, independently verifiable active C2 or operator infrastructure beyond behavioural patterns.

These gaps define the priority for future open-source collection. Further public progress will most likely come from:
1. New technical advisories with IOCs
2. Additional leaks or opposition reporting on internal structure
3. Correlation of academic / research networks with operational activity

---

## Sources

See [`SOURCES.md`](../SOURCES.md) and the individual group/campaign files.  
Key additional references for this document:  
- Orion Policy CyberAv3ngers profile  
- OpenAI disruption report (2024)  
- CISA AA26-097A & AA23-335A  
- CERTFR-2026-CTI-009  
- Lab Dookhtegan / Iran International / Sky News historical reporting (2020–2021)  
- DomainTools Investigations on CyberAv3ngers domains and propaganda shift  
- Public analysis of CyberbanNews Telegram messaging strategy  
- Jerusalem Post / Intelli Times reporting on Lashgarian academic activity  

*Last updated: 2026-11-10 · Public sources only · Evidence-first*
