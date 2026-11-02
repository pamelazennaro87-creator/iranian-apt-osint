# Iranian APT OSINT

**Dossier OSINT operativo su attori cyber allineati allo Stato iraniano (IRGC / MOIS).**  
Solo fonti pubbliche. Orientato a indagine, difesa e riferimento professionale.

> Claims are tested, not collected.  
> Preserve the fingerprint, not the stolen payload.

---

## A chi serve

| Utente | Utilità |
|--------|--------|
| Investigatori / forze dell’ordine | Orientamento rapido, discriminanti tra cluster, checklist IR |
| SOC / detection engineering | Segnali comportamentali duraturi (RMM, edge, OT, canali non tradizionali) |
| Analisti CTI / ricercatori OSINT | Sintesi strutturata 2024–2026, gap nelle narrazioni pubbliche |

**Non è:** intelligence classificata, feed di IOC da “block & forget”, né prova giudiziaria autonoma.

---

## Cosa offre (valore aggiunto)

1. **Profili distinti** — non un generico “Iranian APT”, ma cluster con sponsor tipici, TTPs e limiti di confidenza  
2. **Segnali duraturi** — RMM, edge exploitation, PLC esposti, egress satellitare, shared hosting — prioritari rispetto a IP a breve vita  
3. **Correlazione geopolitica 2026** — pre-posizionamento, downtime selettivi, resilienza sotto conflitto USA/Israele–Iran  
4. **Checklist operative con esempi** — domande e passi concreti per IR e hunting  
5. **Prospettive poco enfatizzate** — eterogeneità tra cluster, peso del pre-posizionamento, bias di visibilità, fragilità attributiva in crisi  

Tutto ancorato a advisory e report pubblici (CISA/FBI, Semperis, ESET, Unit 42, ecc.).

---

## Navigazione rapida

### Per chi indaga ora
| Documento | Contenuto |
|-----------|-----------|
| [`analysis/investigative-questions-checklist.md`](analysis/investigative-questions-checklist.md) | Domande + checklist + mini-playbook con esempi |
| [`analysis/investigative-priorities.md`](analysis/investigative-priorities.md) | Segnali prioritari (RMM, edge, OT, overlap) |
| [`analysis/what-is-missing-2026.md`](analysis/what-is-missing-2026.md) | Cosa le narrazioni pubbliche sottopesano |

### Analisi di profondità
| Documento | Contenuto |
|-----------|-----------|
| [`analysis/geopolitical-cyber-correlation-2026.md`](analysis/geopolitical-cyber-correlation-2026.md) | Timeline cinetico–cyber 2026 |
| [`analysis/prince-of-persia-detailed.md`](analysis/prince-of-persia-detailed.md) | Caso C2 su shared hosting USA |
| [`analysis/starlink-iranian-actors.md`](analysis/starlink-iranian-actors.md) + [`starlink-hunting-notes.md`](analysis/starlink-hunting-notes.md) | Starlink come C2 e come lure |
| [`analysis/divergent-connections.md`](analysis/divergent-connections.md) | Angoli poco esplorati |
| [`analysis/aggressive-research-agenda.md`](analysis/aggressive-research-agenda.md) | Fronti di ricerca prioritari |

### Profili attori
| Gruppo | Note | Path |
|--------|------|------|
| MuddyWater | RMM, Starlink, possibile MaaS, access sharing | [`groups/muddywater.md`](groups/muddywater.md) |
| Fox Kitten | Access broker + ransomware affiliates | [`groups/fox-kitten.md`](groups/fox-kitten.md) |
| Prince of Persia | Caso infrastrutturale 2026 | [`groups/prince-of-persia.md`](groups/prince-of-persia.md) |
| CyberAv3ngers | OT/PLC, IRGC-CEC | [`groups/cyberav3ngers.md`](groups/cyberav3ngers.md) |
| APT35, APT34, APT33, others | Profili di base | `groups/` |

### IOC pubblici
- [`iocs/prince-of-persia-2026.md`](iocs/prince-of-persia-2026.md) — Namecheap / Tornado (Semperis)  
- [`iocs/cyberav3ngers-public-ips.md`](iocs/cyberav3ngers-public-ips.md) — indicatori pubblici OT (dove presenti)  

---

## Struttura del repository

```
iranian-apt-osint/
├── README.md                 ← questo file
├── methodology.md            ← gerarchia fonti, confidenza, limiti
├── groups/                   ← profili attori
├── iocs/                     ← indicatori pubblici contestualizzati
├── analysis/                 ← geopolitica, gap, checklist, Starlink, overlaps
├── campaigns/                ← indici temporali (dove presenti)
└── infrastructure/           ← pattern hosting / geolocalizzazione
```

---

## Metodologia (sintesi)

Dettaglio completo: [`methodology.md`](methodology.md).

- Fonti primaria preferite (advisory governative → vendor tecnici → secondarie verificate)  
- Livelli di confidenza espliciti (High / Medium / Low)  
- Solo IOC già pubblici, con contesto temporale  
- Nessun sample malware, nessun indicatore non pubblico  
- Nessun collegamento inventato tra cluster  

---

## Limiti (da leggere)

- Non sostituisce telemetria, forensics o indagini con poteri di polizia  
- Gli IOC storici vanno rivalidati prima di qualsiasi azione  
- L’attribuzione a sponsor statale resta a confidenza variabile e non è prova legale da sola  
- Il repository va aggiornato man mano che esce nuova ricerca pubblica  

---

## Status

**Ultimo aggiornamento strutturale:** 2026-11-02  

Incluso: profili chiave, caso Prince of Persia 2026, Starlink, correlazione geopolitica, checklist IR con esempi, agenda di ricerca, analisi “what is missing”.

---

*Independent OSINT research · Defensive and investigative reference only · Public sources only*
