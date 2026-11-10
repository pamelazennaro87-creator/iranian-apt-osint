# CyberAv3ngers

**Also known as:** Cyber Avengers, CyberAveng3rs, Shahid Kaveh Group, Hydro Kitten, Storm-0784, Bauxite, Soldiers of Solomon (linked persona), UNC5691, APT Iran, Mr. Soul (persona)

**Likely affiliation:** IRGC Cyber-Electronic Command (IRGC-CEC) — **High confidence**  
(CISA, FBI, NSA, EPA, Treasury sanctions of six IRGC-CEC officials in Feb 2024; joint advisories AA23-335A and AA26-097A; **official French attribution 9 November 2026**)

**First observed:** ~2020 (propaganda persona); significant operational activity from late 2023  
**Primary motivation:** Disruptive / symbolic attacks against critical infrastructure, with strong anti-Israel messaging and later expansion to US and other Western OT targets

> **Update 10 Nov 2026:** French authorities officially attributed the October 2026 supermarket refrigeration sabotage campaign to the **Shahid Kaveh** unit of IRGC-CEC, naming three senior figures. CyberAv3ngers is treated in public reporting as the primary persona / claim front of this unit.  
> Full leadership dossier → [`groups/shahid-kaveh.md`](shahid-kaveh.md)  
> Campaign summary → [`campaigns/france-refrigeration-2026.md`](../campaigns/france-refrigeration-2026.md)

---

## Overview

CyberAv3ngers operates in a different lane from the long-dwell espionage clusters (OilRig, Charming Kitten, classic MuddyWater). It focuses on **internet-exposed industrial control systems**, particularly programmable logic controllers (PLCs) and HMIs. Early activity mixed exaggerated or false claims with real but relatively low-sophistication compromises. Capability has escalated over time from default-credential exploitation to custom OT malware (IOCONTROL) and more advanced abuse of engineering software against Rockwell, Schneider and Siemens devices.

---

## Targeting Profile

- Water and wastewater systems (primary early focus)
- Energy and other critical infrastructure
- Internet-facing PLCs and HMIs (Unitronics Vision Series historically; later Rockwell Automation / Allen-Bradley, Schneider Electric, Siemens)
- Geographic focus: United States, Israel, United Kingdom, Ireland, **France (2026 refrigeration campaign)** and other locations with exposed industrial equipment

---

## Notable Campaign Windows (Public)

| Period | Activity | Notes |
|--------|----------|-------|
| 2020–2022 | Propaganda persona (“Cyber Avengers”) | Many claims against Israeli infrastructure assessed as false or unproven |
| Sep–Oct 2023 | Rebrand to CyberAv3ngers; Telegram + domain registration | Persona domains registered via Namecheap |
| 22 Nov 2023 – Jan 2024 | Unitronics Vision Series PLC campaign | At least 75 devices compromised (≥34 in US water/wastewater). Default credentials on TCP/20256. Defacement messages. Four waves reported. |
| 2024–2025 | IOCONTROL malware deployment | Custom Linux-based OT/IoT malware using MQTT over TLS; broader device types |
| Jan 2025 – Mar 2026 | Staging / scanning against Rockwell devices | Actor-associated IPs observed against internet-facing Rockwell PLCs |
| Mar/Apr 2026 onward | Expanded PLC disruption campaign (AA26-097A) | Rockwell Logix (incl. CVE-2021-22681), later Schneider and Siemens |
| **11–12 Oct 2026** | **French supermarket refrigeration sabotage** | ~700 commercial sites. Official French attribution to Shahid Kaveh / IRGC-CEC (9 Nov 2026) |

---

## Modus Operandi – Key Characteristics

### Initial Access
- Primary vector: **internet-exposed devices with default or weak credentials** (especially early Unitronics campaign – default password “1111” widely reported).
- Later: more deliberate exploitation and use of legitimate vendor engineering software (Studio 5000 Logix Designer / FactoryTalk) installed on leased overseas VPS to blend with authorized engineering sessions.

### Impact Actions
- HMI/screen defacement
- Password and IP changes to lock out operators
- Manipulation of displayed process data / temperature settings (refrigeration controllers, 2026)
- Disruption of communications or control functions
- In some later activity: alteration of logic / disabling of safety-related functions

### Tooling Evolution
- Phase 1: Manual / scripted default-credential access + defacement
- Phase 2: IOCONTROL (MQTT-based, DoH, AES-encrypted config)
- Phase 3: Abuse of official engineering tools from VPS infrastructure for higher-impact multi-vendor operations

---

## Infrastructure & Geolocation Notes (Public)

- **Persona domains** (cyberav3ngers.com / .org / .net): Registered via Namecheap with privacy protection shortly after the 2023 rebrand.
- **Operational infrastructure**: Leased overseas VPS used to host vendor engineering software.
- One publicly mentioned range associated with later activity: **185.82.73.160–171** (and additional IPs in some industry write-ups). Always verify against current advisories.
- C2 characteristics for IOCONTROL: MQTT over TLS (commonly port 8883), DNS-over-HTTPS.

**Geolocation takeaway:** The interesting signal is less “country of IP” and more **type of infrastructure** (overseas VPS running specific engineering software + patterns of scanning for exposed PLC ports).

---

## Where They Err (OPSEC & Operational Failures) – Investigative Value

1. **Heavy reliance on default credentials and internet exposure**  
2. **Exaggerated / false public claims** (especially early period)  
3. **Predictable targeting of known vulnerable product classes**  
4. **Use of distinctive legitimate tools from unusual locations**  
5. **AI-assisted reconnaissance (reported)**  
6. **Propaganda-operational coupling**  

---

## Investigative Notes (LE / Defensive Value)

- Highest-yield defensive actions remain: eliminate internet exposure of PLCs/HMIs, change all default credentials, and monitor for unexpected engineering-software connections from non-standard source ranges.
- The group’s evolution shows a clear learning curve: from “scan + default password + deface” to custom malware and abuse of trusted engineering tools.
- Overlap with other IRGC-CEC personas should be treated as part of a broader ecosystem rather than fully independent actors.
- Treasury sanctions and the November 2026 French attribution + arrest warrants indicate high priority for disruption and attribution by Western governments.

---

## Key Public Resources

- CISA/FBI/NSA/EPA et al. AA23-335A (Unitronics campaign)
- Joint advisory AA26-097A (2026 multi-vendor PLC activity)
- US Treasury sanctions (Feb 2024) on IRGC-CEC officials
- **CERT-FR / C4 – CERTFR-2026-CTI-009 + French MFA attribution (9 Nov 2026)**
- Claroty / Dragos / Unit 42 industry reporting
- MITRE ATT&CK G1027

---

## Status in this repository

- [x] Full profile with campaign timeline
- [x] Explicit link to Shahid Kaveh leadership dossier (French attribution)
- [x] Infrastructure and OPSEC notes
- [ ] Additional high-confidence public IOCs as new advisories release them

*Last updated: 2026-11-10*
