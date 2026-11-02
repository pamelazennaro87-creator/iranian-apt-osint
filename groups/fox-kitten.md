# Fox Kitten (Pioneer Kitten)

**Also known as:** Pioneer Kitten, UNC757, Parisite, RUBIDIUM, Lemon Sandstorm  
**Monikers observed:** Br0k3r, xplfinder  
**Front entity (assessed):** Danesh Novin Sahand (Iranian IT company cover)

**Likely affiliation:** Government of Iran (High confidence – joint FBI/CISA/DC3 advisory AA24-241A, August 2024)  
**First observed:** ~2017  
**Primary motivations:** 
1. Espionage in support of Iranian government objectives  
2. **Initial access brokerage** to ransomware affiliates (ALPHV/BlackCat, NoEscape, RansomHouse and others) – assessed by FBI as likely not fully sanctioned activity running in parallel

---

## Why this cluster matters for investigations

Fox Kitten is one of the highest-value Iranian clusters from a law-enforcement and incident-response perspective because of its **dual role**:

- It conducts state-aligned espionage.
- It simultaneously acts as an access broker, selling or sharing network access with ransomware groups.

This means a ransomware incident (especially involving the named affiliates) can have an upstream Iranian initial-access component. Conversely, an apparent “criminal” intrusion may actually originate from state-linked edge exploitation.

---

## Targeting Profile

- Education, finance, healthcare, defense, local government
- Geographic focus includes United States, Middle East (Israel, UAE, Azerbaijan and others), Europe, Australia
- Heavy emphasis on **edge devices** rather than pure phishing

---

## Core TTPs

### Initial Access
- Exploitation of vulnerabilities in VPN and network appliances:
  - Citrix NetScaler / ADC
  - Ivanti / Pulse Secure
  - F5 BIG-IP
  - Palo Alto PAN-OS
  - Check Point Security Gateway
- Known CVEs leveraged in recent years include (non-exhaustive): CVE-2023-3519, CVE-2024-21887, CVE-2024-3400, CVE-2024-24919, CVE-2022-1388 and others as they appear.

### Post-Exploitation & Persistence
- Web shells placed in obscure or rarely monitored paths (example pattern reported: `/var/vpn/themes/imgs/` and similar)
- Preference for living-off-the-land and fileless techniques
- Use of tunneling tools (Ligolo, socat, proxychains)
- Deployment of post-exploitation frameworks (Havoc, MeshCentral, custom C2)

### Access Brokerage
- Access (sometimes full domain admin) offered or transferred to ransomware affiliates
- Collaboration observed with ALPHV/BlackCat, NoEscape, RansomHouse
- FBI assesses the ransomware collaboration is likely separate from pure government tasking

---

## Investigative Notes

1. **Ransomware cases** involving the above affiliates should be checked for upstream edge-device compromise consistent with Fox Kitten TTPs.
2. Patching a vulnerable appliance **does not automatically remove** existing webshells or stolen credentials – full investigation of the device and any lateral movement is required.
3. Look for webshells in non-standard directories on VPN/edge devices and for unusual tunneling or SOCKS proxy activity.
4. The dual espionage + criminal access model creates attribution ambiguity that can be exploited by the actors and must be carefully handled in reporting.

---

## Key Public Resources

- Joint FBI / CISA / DC3 advisory **AA24-241A** (28 August 2024)
- MITRE ATT&CK G0117
- Supporting industry analysis (Censys infrastructure notes, vendor reporting on edge exploitation)

---

## Status in this repository

- [x] Profile focused on access-broker role and investigative value
- [ ] Additional public IOC enrichment as high-confidence sets become available
- [ ] Cross-link with ransomware affiliate activity where publicly documented

*Last updated: 2026-11-02*
