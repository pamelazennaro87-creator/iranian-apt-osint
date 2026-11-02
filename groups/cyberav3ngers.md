# CyberAv3ngers

**Also known as:** Cyber Avengers, CyberAveng3rs, Shahid Kaveh Group, Hydro Kitten, Storm-0784, Bauxite, Soldiers of Solomon (linked persona), UNC5691, APT Iran, Mr. Soul (persona)

**Likely affiliation:** IRGC Cyber-Electronic Command (IRGC-CEC) — **High confidence**  
(CISA, FBI, NSA, EPA, Treasury sanctions of six IRGC-CEC officials in Feb 2024; joint advisories AA23-335A and AA26-097A)

**First observed:** ~2020 (propaganda persona); significant operational activity from late 2023  
**Primary motivation:** Disruptive / symbolic attacks against critical infrastructure, with strong anti-Israel messaging and later expansion to US and other Western OT targets

---

## Overview

CyberAv3ngers operates in a different lane from the long-dwell espionage clusters (OilRig, Charming Kitten, classic MuddyWater). It focuses on **internet-exposed industrial control systems**, particularly programmable logic controllers (PLCs) and HMIs. Early activity mixed exaggerated or false claims with real but relatively low-sophistication compromises. Capability has escalated over time from default-credential exploitation to custom OT malware (IOCONTROL) and more advanced abuse of engineering software against Rockwell, Schneider and Siemens devices.

---

## Targeting Profile

- Water and wastewater systems (primary early focus)
- Energy and other critical infrastructure
- Internet-facing PLCs and HMIs (Unitronics Vision Series historically; later Rockwell Automation / Allen-Bradley, Schneider Electric, Siemens)
- Geographic focus: United States, Israel, United Kingdom, Ireland and other locations with exposed Israeli-made or widely deployed industrial equipment

---

## Notable Campaign Windows (Public)

| Period | Activity | Notes |
|--------|----------|-------|
| 2020–2022 | Propaganda persona (“Cyber Avengers”) | Many claims against Israeli infrastructure assessed as false or unproven |
| Sep–Oct 2023 | Rebrand to CyberAv3ngers; Telegram + domain registration | Persona domains registered via Namecheap |
| 22 Nov 2023 – Jan 2024 | Unitronics Vision Series PLC campaign | At least 75 devices compromised ( ≥34 in US water/wastewater). Default credentials on TCP/20256. Defacement messages. Four waves reported. |
| 2024–2025 | IOCONTROL malware deployment | Custom Linux-based OT/IoT malware using MQTT over TLS; broader device types (cameras, routers, fuel systems, etc.) |
| Jan 2025 – Mar 2026 | Staging / scanning against Rockwell devices | Actor-associated IPs observed against internet-facing Rockwell PLCs |
| Mar/Apr 2026 onward | Expanded PLC disruption campaign (AA26-097A) | Rockwell Logix (incl. CVE-2021-22681), later Schneider and Siemens added. False HMI/SCADA data, disabled alarms/shutdown logic reported in some cases |

---

## Modus Operandi – Key Characteristics

### Initial Access
- Primary vector: **internet-exposed devices with default or weak credentials** (especially early Unitronics campaign – default password “1111” widely reported).
- Later: more deliberate exploitation and use of legitimate vendor engineering software (Studio 5000 Logix Designer / FactoryTalk) installed on leased overseas VPS to blend with authorized engineering sessions.

### Impact Actions
- HMI/screen defacement
- Password and IP changes to lock out operators
- Manipulation of displayed process data
- Disruption of communications or control functions
- In some later activity: alteration of logic / disabling of safety-related functions

### Tooling Evolution
- Phase 1: Manual / scripted default-credential access + defacement
- Phase 2: IOCONTROL (MQTT-based, DoH, AES-encrypted config) – more persistent and stealthy OT foothold
- Phase 3: Abuse of official engineering tools from VPS infrastructure for higher-impact Rockwell (and later multi-vendor) operations

---

## Infrastructure & Geolocation Notes (Public)

- **Persona domains** (cyberav3ngers.com / .org / .net): Registered via Namecheap with privacy protection shortly after the 2023 rebrand. Largely symbolic; little evidence of heavy operational use as C2.
- **Operational infrastructure**: Leased overseas VPS used to host vendor engineering software. Source IPs described in public reporting as non-residential and concentrated outside normal victim business geographies.
- One publicly mentioned range associated with later activity: **185.82.73.160–171** (and additional IPs such as 135.136.1.133 in some industry write-ups). Always verify against current advisories (AA26-097A and updates).
- C2 characteristics for IOCONTROL: MQTT over TLS (commonly port 8883), DNS-over-HTTPS for resolution – designed to blend with legitimate IoT traffic.

**Geolocation takeaway:** The interesting signal is less “country of IP” and more **type of infrastructure** (overseas VPS running specific engineering software + patterns of scanning for exposed PLC ports).

---

## Where They Err (OPSEC & Operational Failures) – Investigative Value

These are the publicly observable weaknesses most useful for detection and investigation:

1. **Heavy reliance on default credentials and internet exposure**  
   Early success depended almost entirely on victims leaving Unitronics devices on the public internet with factory defaults. This is both their greatest enabler and a major limiting factor in sophistication.

2. **Exaggerated / false public claims**  
   Particularly in the Soldiers of Solomon / early Cyber Avengers period, many claimed compromises of Israeli critical infrastructure were assessed as false. This creates noise but also provides persona and messaging consistency that can be tracked.

3. **Predictable targeting of known vulnerable product classes**  
   Repeated focus on the same device families (Unitronics → Rockwell → expansion to Schneider/Siemens) allows defenders to prioritize exposure reduction and monitoring of specific ports (20256, 44818, 2222, 102, 502, etc.).

4. **Use of distinctive legitimate tools from unusual locations**  
   Running Studio 5000 / FactoryTalk from overseas VPS infrastructure creates a behavioral signal: engineering software connections originating from atypical geographies or hosting providers.

5. **AI-assisted reconnaissance (reported)**  
   OpenAI disclosed that accounts linked to the group used ChatGPT for ICS-related queries (default credentials, scanning methods, Modbus, etc.). This is an OPSEC residual that can appear in provider logs.

6. **Propaganda-operational coupling**  
   Public Telegram messaging and defacement content often closely tracks real activity windows, reducing the separation between influence operations and technical operations.

---

## Investigative Notes (LE / Defensive Value)

- Highest-yield defensive actions remain: eliminate internet exposure of PLCs/HMIs, change all default credentials, and monitor for unexpected engineering-software connections from non-standard source ranges.
- The group’s evolution shows a clear learning curve: from “scan + default password + deface” to custom malware and abuse of trusted engineering tools. Future activity is likely to continue expanding vendor coverage.
- Overlap with other IRGC-CEC personas (Soldiers of Solomon, Moses Staff infrastructure links reported by some researchers) should be treated as part of a broader ecosystem rather than fully independent actors.
- Treasury sanctions and Rewards for Justice actions indicate the US government treats this cluster as a priority for disruption and attribution.

---

## Key Public Resources

- CISA/FBI/NSA/EPA et al. AA23-335A (Unitronics campaign, updated Dec 2024)
- Joint advisory AA26-097A (2026 multi-vendor PLC activity)
- US Treasury sanctions (Feb 2024) on IRGC-CEC officials
- Claroty / Dragos / Unit 42 industry reporting on IOCONTROL and later activity
- MITRE ATT&CK G1027

---

## Status in this repository

- [x] Full profile with campaign timeline
- [x] Infrastructure and geolocation notes
- [x] Explicit OPSEC / error analysis for investigative use
- [ ] Additional high-confidence public IOCs as new advisories release them

*Last updated: 2026-11-02*
