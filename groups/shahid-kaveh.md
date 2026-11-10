# Shahid Kaveh

**Also known as / linked personas:** CyberAv3ngers / CyberAveng3rs, Cyber Isnaad Front, Soldiers of Solomon, CyberbanNews, Mr. Soul, Hydro Kitten, Bauxite, UNC5691, Storm-0784 (partial overlap in public reporting)

**Affiliation:** Offensive cyber unit under the **IRGC Cyber-Electronic Command (IRGC-CEC / CGRI-CEC)**  
**Confidence:** High (official French attribution, 9 November 2026 + prior US Treasury sanctions)

**Primary public attribution event:** French supermarket refrigeration sabotage campaign (11–12 October 2026)

---

## Official Attribution (France – 9 November 2026)

On 9 November 2026 the French authorities (Parquet de Paris, CERT-FR / C4, Ministère de l’Europe et des Affaires étrangères) publicly attributed a large-scale cyber-sabotage operation against commercial refrigeration controllers to the unit **Shahid Kaveh**.

### Key facts from official statements
- **Targets:** ~700 commercial sites across France (mainly supermarkets, also butcher shops, a slaughterhouse and food-processing facilities). Controllers reported as including Danfoss and Dixell equipment.
- **Impact:** Remote manipulation of refrigeration controllers (raising temperatures, in some cases to ~50°C), leading to massive food spoilage and at least 15 fires. Estimated losses in the tens of millions of euros.
- **Date of attack:** Night of 11–12 October 2026.
- **Attribution basis (publicly stated by C4 / CERT-FR):**  
  - Re-use of digital infrastructure previously associated with the unit  
  - Matching intrusion patterns  
  - Traces of Farsi/Persian language in the attack infrastructure  
  - Propaganda outlets linked to the unit (notably CyberbanNews)  
  - Technical indicators consistent with prior Shahid Kaveh / CyberAv3ngers activity
  - Use of FOFA scanning tool noted in some reporting

The Paris Prosecutor’s Office opened a judicial investigation and requested **international arrest warrants** for the three individuals named below.

---

## Named Leadership (Public French Attribution + Open Identifiers)

### 1. Hamid Reza Lashgarian (حمیدرضا لشگریان / Hamidreza Lashgarian)
- **Role (French attribution):** Head of the IRGC Cyber-Electronic Command (IRGC-CEC / CGRI-CEC)
- **Public identifiers (OFAC & open reporting):**
  - DOB: 21 March 1961 (Tehran)
  - National ID: 0046455922
  - Passports: D10006686, N46460034, D10012058
  - OFAC SDN since 2 February 2024 (SDGT / IRGC / IFSR)
  - Rewards for Justice: up to $10 million (re-listed 2026)
  - Linked in open sources to Quds Force cyber/intelligence activity and research centres (Kavosh, Nasr, Kousar Com, Deep Com Asia)
- **Confidence:** High

### 2. Mahdi Lashgarian (مهدی لشگریان / Mehdi Lashgarian)
- **Role (French attribution):** Commander of the Shahid Kaveh unit
- **Public identifiers (OFAC & open reporting):**
  - DOB: 2 June 1989
  - National ID: 0010365044
  - Passport: M56717088
  - Birth Certificate Number: 136544
  - OFAC SDN since 2 February 2024 (same package as Hamid Reza)
  - Reported family link (nephew) to Hamid Reza Lashgarian in open-source analyses
- **Confidence:** High for role; Medium for family relationship details

### 3. Reza Salarvand
- **Role (French attribution):** Commander of the Shahid Kaveh unit
- **Public information:**
  - Linked in open sources to Intelligence Group / Team 13 (تیم اطلاعاتی ۱۳) tactical operations
  - Education details (IT Engineering, Azad University – South Branch, Tehran, ~2017) reported via opposition media leaks (Lab Dookhtegan / Iran International)
  - Not individually listed in the February 2024 OFAC package
- **Confidence:** High for the French attribution; Medium for deeper biographical details

> **Important:** All names, roles and identifiers above come exclusively from official French statements, OFAC public listings, and subsequent reputable open reporting. No non-public sources were used.

---

## Technical Notes from CERT-FR (Public)

According to CERTFR-2026-CTI-009:
- Shahid Kaveh has, at least since June 2024, possessed scripts allowing scanning, access and control of industrial control equipment from Schneider Electric, Siemens and Rockwell.
- In April 2026 the unit was observed using the Modbus protocol on port 502 for large-scale reconnaissance against Schneider Electric industrial control systems, including targets in France.
- The unit operates primarily through digital hacktivist avatars (CyberAveng3rs, Soldiers of Solomon, Mr. Soul, Cyber Isnaad Front) and the online outlet CyberbanNews.

---

## Relationship to CyberAv3ngers & Sister Units

Public French reporting and prior Western advisories treat **Shahid Kaveh** as the operational unit and **CyberAv3ngers** (and related personas) as the public-facing / propaganda and claim front used by the same IRGC-CEC structure.

A sister unit under the same IRGC-CEC umbrella, **Shahid Shoostari**, has been publicly linked by French authorities to earlier influence / disruption operations (including activity related to Charlie Hebdo in 2020 and 2023).

See also: [`groups/cyberav3ngers.md`](cyberav3ngers.md)

---

## Historical Context (Public)

- Named after IRGC commander Mohammad Kaveh (killed 1986, Iran–Iraq War, age 25).
- Specialised in disruptive operations against industrial and critical infrastructure.
- Prior publicly linked activity includes:
  - Unitronics Vision Series PLC campaign (Nov 2023 – early 2024)
  - Broader OT targeting reported in 2024–2026 CISA advisories
  - Claimed sabotage campaigns against Israeli and US industrial equipment (March–April 2026)

---

## Sources

Full source list: [`SOURCES.md`](../SOURCES.md)

Primary:
- CERT-FR / C4 – CERTFR-2026-CTI-009 (9 Nov 2026)
- Parquet de Paris & French MFA statements (9–10 Nov 2026)
- US Treasury OFAC (2 Feb 2024)
- CISA AA23-335A & AA26-097A

---

## Status in this repository

- [x] Leadership dossier based on official French attribution + public OFAC identifiers
- [x] Technical notes from CERT-FR
- [x] Explicit public-sources-only methodology
- [x] Cross-link to CyberAv3ngers profile and SOURCES.md
- [ ] Additional technical IOCs as new public advisories appear

*Last updated: 2026-11-10*

---

*Independent OSINT research · Public sources only · Evidence-first*
