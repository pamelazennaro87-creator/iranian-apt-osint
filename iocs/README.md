# Public Indicators of Compromise (IOCs)

**Strict rules for this directory:**

1. Only indicators that have already been **publicly published** by reputable researchers, vendors, or governments are collected here.
2. Every indicator must include source and, where available, association time window.
3. No private or unverified indicators.
4. Prefer high-confidence, well-sourced data.
5. This is a **defensive / investigative reference** collection.

---

## Available Collections

| File | Content |
|------|---------|
| [public-examples.md](public-examples.md) | Curated examples (Prince of Persia, APT35, MuddyWater) |
| [cyberav3ngers-public-ips.md](cyberav3ngers-public-ips.md) | **Full public IP list** from CISA AA26-097A (operator workstation cluster 185.82.73.x, staging hosts, association windows) + limited AA23-335A context |

---

## Highest-Value Current Set

The **CyberAv3ngers / AA26-097A** IP collection is the most complete officially sourced set currently in the repository. It includes:

- Operator engineering workstation cluster (185.82.73.x range)
- Additional staging and related addresses with time windows
- Clear usage guidance for defenders and investigators

Always re-verify current status of any IP before operational use. CISA itself recommends investigation/vetting prior to blocking.

---

*All indicators remain the intellectual property of their original publishers. Aggregated here for defensive and investigative convenience.*
