# CyberAv3ngers / Iranian-Affiliated PLC Activity – Public IP Indicators

**Source hierarchy:** Primary indicators taken from official CISA joint advisory **AA26-097A** (April 2026, updated July 2026) and supporting public analysis (Censys and others).  
All indicators below are already in the public domain. They are provided for defensive monitoring, log hunting, and investigative reference by authorized entities.

**Important:** CISA explicitly recommends organizations **investigate and vet** these addresses before blocking. Many have limited association windows. Infrastructure turns over; always cross-check current passive DNS / reputation sources.

---

## AA26-097A – Primary Public IP Indicators (CISA)

### Operator / Engineering Infrastructure Cluster

These addresses were associated with the threat actor’s use of legitimate Rockwell engineering software (Studio 5000 / FactoryTalk) against internet-exposed PLCs.

| IP Address | Association Window (approx.) | Notes |
|------------|------------------------------|-------|
| 185.82.73.162 | Jan 2025 – Mar 2026 | Part of multi-homed operator workstation cluster (AS214036 ULTAHOST) |
| 185.82.73.164 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.165 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.167 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.168 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.170 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.171 | Jan 2025 – Mar 2026 | Same cluster |
| 185.82.73.175 | Sep 2025 – Feb 2026 | Related activity |

**Additional context from public analysis (Censys):**  
The 185.82.73.160–171 range largely resolves to a single multi-homed Windows engineering workstation running the full Rockwell toolchain. Observed characteristics include RDP on non-standard port 43589 and self-signed certificate CN `DESKTOP-BOE5MUC`. Some adjacent IPs in the same range share the same fingerprint and were noted by researchers even if not all appear in the original advisory table.

### Additional / Staging Addresses (AA26-097A)

| IP Address | Association Window (approx.) | Notes |
|------------|------------------------------|-------|
| 135.136.1.133 | Mar 2026 | Short-lived staging host (reported AS9009 / M247 Romania) |
| 141.11.164.153 | Jan 2026 – Jun 2026 | |
| 175.110.121.42 | Feb 2026 – Mar 2026 | |
| 175.110.121.39 | Feb 2026 – Mar 2026 | |
| 175.110.121.41 | Feb 2026 – Mar 2026 | |
| 175.110.121.107 | Feb 2026 | |
| 192.142.54.79 | May 2026 – Jun 2026 | |
| 84.200.205.165 | May 2026 – Jun 2026 | |
| 185.225.17.225 | Jun 2026 – Jul 2026 | |
| 79.133.46.209 | Jul 2026 | |
| 88.80.150.199 | Jul 2026 | |
| 88.80.150.200 | Jul 2026 | |
| 88.80.150.202 | Jul 2026 | |

---

## Earlier Related Activity (AA23-335A – Unitronics campaign context)

Limited public IP indicators were published in the 2023 Unitronics advisory. Two addresses were listed in connection with related ransomware tooling observations (fidelity marked “Suspected” in the original advisory):

- 178.162.227.180
- 185.162.235.206

These should be treated with lower confidence and only in the specific historical context of the 2023 activity.

---

## Prince of Persia (separate cluster – for cross-reference)

Publicly reported by Semperis (Oct 2026):

| IP Address | Context |
|------------|---------|
| 68.65.122.203 | Tornado second-stage C2, Namecheap shared hosting (AS22612), active ~Jul 2026 |

---

## Usage Guidance for Investigators / Defenders

1. Prefer **historical log searches** over immediate broad blocking, especially for the longer-window addresses.
2. Correlate any hits with OT-relevant ports (44818, 2222, 102, 502, 22, 20256) and with the presence of vendor engineering software traffic.
3. The most durable signal remains behavioral: legitimate engineering tools (Studio 5000, FactoryTalk, EcoStruxure, TIA Portal) originating from atypical VPS / overseas hosting ranges.
4. Always re-verify current status of any IP before operational use.

---

**Primary sources:**  
- CISA AA26-097A (April 2026, updated July 2026)  
- CISA AA23-335A (2023 Unitronics)  
- Supporting public analysis: Censys, industry reporting referencing the same advisory tables  
- Semperis (Prince of Persia 2026)

*This collection contains only indicators already released in official or widely cited public reporting. Last reviewed: 2026-11-02.*
