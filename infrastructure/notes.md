# Infrastructure & Hosting Patterns (Public Observations)

This file collects **publicly reported** patterns in Iranian APT infrastructure. All entries are derived from published research. No private or unverified data.

---

## General Patterns Across Clusters

Iranian actors show recurring preferences that appear across multiple groups:

- Heavy use of **NameCheap**, **NameSilo**, and similar low-friction registrars for domains.
- Frequent short-lived domains and rapid infrastructure turnover (especially Charming Kitten and MuddyWater).
- Preference for European and Middle Eastern VPS providers historically, with occasional shifts.
- Increasing abuse of legitimate services (Microsoft 365, OneDrive, Telegram, Cloudflare, commercial RMM tools).
- Use of shared hosting to blend with legitimate traffic (notably observed with Prince of Persia in 2026).
- Occasional domestic Iranian infrastructure visible in leaked operational material (Charming Kitten 2025 leak).

---

## Group-Specific Public Notes

### APT35 / Charming Kitten
- Long history of credential-phishing domains mimicking major providers (Google, Microsoft, Yahoo, etc.).
- 2025 KittenBusters leak exposed extensive internal infrastructure documentation, procurement identities, and operational servers.
- Documented use of both international VPS and some domestic Iranian network allocations in operational material.
- Frequent persona development and multi-stage social engineering before payload delivery.

### MuddyWater
- Strong preference for legitimate Remote Monitoring & Management (RMM) tools (ConnectWise, Syncro, Atera, PDQ, etc.) for persistence.
- Reported use of commercial satellite internet (Starlink) for C2 in late 2025 / early 2026.
- Rapid domain turnover; many domains registered via NameCheap / Hosterdaddy.
- Documented operational overlap with OilRig/Lyceum subgroups (initial access brokerage pattern).

### APT34 / OilRig
- Classic use of DNS tunneling and custom web shells (TwoFace family and variants).
- Staging infrastructure often left dormant for months before activation.
- Historical use of compromised legitimate infrastructure and supply-chain vectors.
- Later campaigns showed increased abuse of Microsoft cloud services.

### Prince of Persia (Infy)
- Historically preferred European VPS ranges.
- **2026 shift**: First documented use of US-based shared hosting (Namecheap) for Tornado second-stage C2 in approximately a decade (Semperis, Oct 2026).
- Publicly reported C2: `68.65.122.203` (AS22612, Namecheap), active ~July 2026.
- Also observed infrastructure behind Cloudflare and use of Telegram API / DGA-style domains.

### CyberAv3ngers
- Focus on internet-exposed ICS/OT devices (notably Unitronics PLCs).
- Public claims frequently exaggerated relative to technical impact.

---

## Geolocation / Hosting Observations (High-Level)

| Pattern | Frequency | Notes |
|---------|-----------|-------|
| European VPS | High (historical) | Common across multiple groups |
| NameCheap / shared hosting | Increasing | Blending technique, harder to sinkhole |
| Cloudflare | Common | Used for obfuscation and resilience |
| US hosting | Rare but documented | Notable 2026 Prince of Persia case |
| Domestic Iranian allocations | Occasional | Visible mainly in leaked operational data |
| Satellite (Starlink) | Emerging | Reported for MuddyWater 2025–2026 |

---

## Research Notes

- Infrastructure is highly dynamic. Any IP or domain list has limited shelf life.
- Shared hosting and CDN usage significantly reduce the value of simple geolocation for attribution.
- The most durable signals remain: tooling families, targeting patterns, operational tempo, and rare unique artifacts (SSH fingerprints, specific panel configurations, code overlaps).

*This section will be expanded as additional high-confidence public research becomes available.*
