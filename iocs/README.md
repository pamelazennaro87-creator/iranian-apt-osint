# Public Indicators of Compromise (IOCs)

**Strict rules for this directory:**

1. Only indicators that have already been **publicly published** by reputable researchers, vendors, or governments are collected here.
2. Every indicator must include:
   - Source (report / advisory / researcher)
   - Approximate date of publication or observation
   - Associated group (with confidence level if ambiguous)
3. No private, leaked-but-not-publicly-analyzed, or unverified indicators.
4. Prefer high-confidence, recently active infrastructure when possible.
5. This is a **defensive** collection for detection engineering and research — not an operational target list.

---

## Structure

- `domains.txt` — Malicious or actor-controlled domains
- `ips.txt` — IP addresses with context
- `hashes.txt` — File hashes (SHA256 preferred)
- Future: `yara/`, `sigma/`, `stix/` as the collection matures

---

## Current Status

🚧 Collection in progress. Initial high-confidence public indicators will be added group-by-group with full source attribution.

**Priority order for population:**
1. APT35 / Charming Kitten (richest public data, including 2025 leak material)
2. MuddyWater (active 2025–2026 campaigns)
3. APT34 / OilRig
4. APT33
5. Remaining clusters

---

*All indicators remain the intellectual property of their original publishers. This repository aggregates them for research convenience under fair-use / defensive purposes.*
