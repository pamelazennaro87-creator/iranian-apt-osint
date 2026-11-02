# Curated Public IOC Examples

**Rules:** Only indicators that have been explicitly published by reputable researchers or vendors are listed. Every entry includes source and approximate date. This is a starting collection for research and detection engineering — not a comprehensive or operational blocklist.

Always verify current status of any indicator before use (infrastructure turns over rapidly).

---

## Prince of Persia (Infy) — 2026

| Type | Indicator | Context | Source | Date |
|------|-----------|---------|--------|------|
| IP | 68.65.122.203 | Tornado second-stage C2, Namecheap shared hosting (AS22612) | Semperis Research | ~Jul–Oct 2026 |
| Domain pattern | *.privatedns.org (examples: kxzsfydnivzmv.privatedns.org and related) | Associated with Tornado C2 | Semperis Research | 2026 |

Additional related infrastructure was observed behind Cloudflare (e.g. 162.159.24.80 range reported in related coverage).

---

## APT35 / Charming Kitten — Selected Public Examples

| Type | Indicator | Context | Source | Date |
|------|-----------|---------|--------|------|
| Hash (SHA256) | 686c40fd7bd9cacd9a9a40dffcc12000f9e3ce6aacfe7d261411ff34e576dcbe | RAND Discussion Topics.lnk (GenAI-assisted lure) | Unit 42 (Agent Serpens / Charming Kitten) | Jun 2025 |
| Hash (SHA256) | 33ea3a8e535e7eea71ffaaab83abef7cea776fcb23376a71c37977ae4be23778 | sin.dll (related to PowerLess activity) | Unit 42 | 2025 |

Large historical domain and IP collections exist in public repositories (e.g. Maltrail trails, JayGLXR/APT35-IOCs, KittenBusters material). These should be treated as research corpora rather than active blocklists due to age and volume.

---

## MuddyWater — Selected Public Examples (from ESET and related 2025 reporting)

| Type | Indicator | Context | Source | Date |
|------|-----------|---------|--------|------|
| IP | 212.232.22.136 | Reported C2 / related infrastructure | ESET-linked collections | ~2025 |
| IP | 194.11.246.78 | Reported C2 | ESET-linked collections | ~2024–2025 |
| Domain | processplanet.org | Staging / C2 association | Public reporting | 2024 |

Note: MuddyWater infrastructure is particularly short-lived. Prefer behavioral detection (RMM abuse, specific loader patterns, PowerShell / Rust toolmarks) over static IOC blocking.

---

## Guidance for Use

1. **Prefer behavioral detections** over pure IOC matching for these actors.
2. Cross-check any IP/domain against current passive DNS and reputation sources before operational use.
3. When expanding this collection, require: (a) named source, (b) approximate observation date, (c) associated group with confidence.
4. Distinguish between “historically associated” and “currently active.”

---

*This file will grow with additional high-confidence, well-sourced public indicators. Contributions should follow the same evidence standard.*
