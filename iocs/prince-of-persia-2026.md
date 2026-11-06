# Prince of Persia – Public IOCs 2026 (Namecheap / US Shared Hosting Case)

**Fonte primaria:** Semperis Research (ottobre 2026)  
**Contesto:** Primo C2 su suolo USA dal 2016; passaggio da VPS a shared hosting Namecheap; cambio pannello da Cyber Panel a cPanel.

> Tutti gli indicatori sono pubblici e già divulgati. Utili per hunting storico e correlazione, non come unico criterio di blocco.

---

## Indicatori principali

### C2 Tornado second-stage (shared hosting Namecheap)

| Tipo | Valore | Note |
|------|--------|------|
| IP | `68.65.122.203` | Attivo da circa luglio 2026 – ASN AS22612 (Namecheap) |
| Domini | `kxzsfydnivzmv.privatedns.org` | Dominio principale osservato |
| | `jqkctsldgwkbw.privatedns.org` | |
| | `emcwoyqtplckl.privatedns.org` | |
| | `izwljrmohqwcq.privatedns.org` | |
| | `bymznpviesmqs.privatedns.org` | |

### Altri IP pubblici collegati al caso

| IP | Contesto |
|----|----------|
| `162.159.24.80` | Secondo C2 Tornado (attivo da ~24 agosto 2026) – dietro Cloudflare |
| `185.244.129.123` | Segnalato nel set di indicatori Semperis |
| `185.244.129.70` | Segnalato nel set di indicatori Semperis |

### IP storici di riferimento (pre-migrazione)

| IP | Note |
|----|------|
| `45.80.148.249` | C2 spento poco dopo pubblicazione ricerca febbraio 2026 |
| `45.80.148.194` | Nuovo C2 attivato 9 febbraio 2026 (stesso range) |
| `45.80.148.195` | Range adiacente osservato |

---

## Caratteristiche infrastrutturali di interesse

- **Hosting:** Namecheap shared hosting (non VPS dedicato) → mescolato a migliaia di domini legittimi e ad altri threat actor (es. typosquatting Roblox).
- **Pannello:** passaggio a **cPanel**.
- **Protezione successiva:** spostamento di parte dell’infrastruttura dietro Cloudflare dopo probabile esposizione.
- **Malware:** famiglia Tornado (second-stage con capacità di furto file via Telegram bot).

---

## Note per hunting e indagini

1. L’IP `68.65.122.203` da solo ha basso valore isolato (shared hosting). Diventa utile in correlazione con i domini `*.privatedns.org` o con traffico Telegram anomalo.
2. Il pattern “VPS → shared hosting Namecheap + cPanel” può essere cercato anche in altri cluster iraniani nello stesso periodo.
3. Monitorare connessioni verso API Telegram da host che non dovrebbero usarle, specialmente in ambienti di interesse.
4. I domini privatedns.org di questo set sono candidati prioritari per sinkhole / monitoring passivo.

---

*Fonte: Semperis “Prince of Persia: A Threat Group Hiding in Plain Sight” e reporting correlato (ottobre 2026). Ultimo aggiornamento repository: 2026-11-02.*


## IOC provenance and freshness — 2026-11-06

The table above is a source-reported historical IOC set, not a live-verified blocklist. The current file does not provide per-indicator first_seen/last_seen timestamps, exact source passages, or a fresh resolution/connection check for every domain and IP. Do not infer those fields from the case-level publication date. Add per-row source reference, source observation date/window, retrieval date, confidence rationale, and current revalidation result before operational use. Where Semperis reports an association, preserve that attribution as “reported by Semperis”; do not promote it to independent confirmation. Shared hosting and Cloudflare-fronted IPs are especially weak as standalone attribution pivots.
