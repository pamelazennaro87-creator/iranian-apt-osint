# Campaign: French Supermarket Refrigeration Sabotage – October 2026

**Actor:** Shahid Kaveh (IRGC-CEC)  
**Confidence of attribution:** High (official French government attribution, 9 November 2026)  
**Date of activity:** Night of 11–12 October 2026  
**Public disclosure:** 9 November 2026

---

## Summary

A coordinated cyber-sabotage operation targeted industrial refrigeration controllers at approximately **700 commercial sites** across France. Attackers remotely altered temperature / defrost settings (in some cases raising temperatures significantly, reported up to ~50°C), causing widespread food spoilage and at least 15 fires. Material losses were estimated in the tens of millions of euros.

This was described by French authorities as the first purely sabotage-oriented offensive cyber campaign of this scale on French soil.

Controllers involved included equipment from manufacturers such as Danfoss and Dixell (public reporting).

---

## Official Attribution

On 9 November 2026 the following French entities publicly attributed the operation to **Shahid Kaveh**, an offensive cyber unit of the IRGC Cyber-Electronic Command (IRGC-CEC / CGRI-CEC):

- Centre de Coordination des Crises Cyber (C4) / CERT-FR (CERTFR-2026-CTI-009)
- Parquet de Paris
- Ministère de l’Europe et des Affaires étrangères

**Named individuals (international arrest warrants requested):**
- Hamid Reza Lashgarian – Head of IRGC-CEC
- Mahdi Lashgarian – Commander, Shahid Kaveh
- Reza Salarvand – Commander, Shahid Kaveh

Full leadership dossier: [`groups/shahid-kaveh.md`](../groups/shahid-kaveh.md)

---

## Technical Context from CERT-FR (Public)

- Shahid Kaveh has possessed, at least since June 2024, scripts allowing scanning, access and control of industrial control equipment from **Schneider Electric, Siemens and Rockwell**.
- In April 2026 the unit was observed using the **Modbus protocol on port 502** for large-scale reconnaissance against Schneider Electric industrial control systems (including targets in France).
- Attribution indicators publicly cited: re-used infrastructure, matching TTPs, Farsi/Persian language traces in attack infrastructure, and claims/propaganda via CyberbanNews and related personas.

No full public IOC list was released in the initial CERT-FR report. Historical public IPs associated with the broader CyberAv3ngers / IRGC-CEC ecosystem are documented in [`iocs/cyberav3ngers-public-ips.md`](../iocs/cyberav3ngers-public-ips.md).

---

## Related Units & Personas

| Entity | Relationship |
|--------|--------------|
| Shahid Kaveh | Operational unit attributed by France |
| CyberAv3ngers / CyberAveng3rs | Primary public-facing persona / claim front |
| CyberbanNews | Online propaganda outlet linked to the unit |
| Shahid Shoostari | Sister unit under the same IRGC-CEC structure (prior activity against Charlie Hebdo and other French targets) |
| IRGC-CEC | Parent command |

---

## Primary Public Sources

Full list: [`SOURCES.md`](../SOURCES.md)

- CERT-FR / C4 – CERTFR-2026-CTI-009 (9 Nov 2026)
- Parquet de Paris official statements (9 Nov 2026)
- French MFA attribution declaration (9–10 Nov 2026)
- Contemporary reporting: Al Jazeera, The National, La Stampa, IranWire, L’Express, franceinfo, Reuters

---

## Status

- [x] Campaign summary based exclusively on official French statements
- [x] Technical notes from CERT-FR
- [x] Cross-linked to leadership dossier, CyberAv3ngers profile and SOURCES.md
- [ ] Expanded technical IOC section pending further public releases

*Created / last updated: 2026-11-10*
