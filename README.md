# Iranian APT OSINT

**Dossier OSINT operativo su attori cyber allineati allo Stato iraniano (IRGC / MOIS).**  
**Solo fonti pubbliche.** Orientato a indagine, difesa e riferimento professionale.

> Claims are tested, not collected.  
> Preserve the fingerprint, not the stolen payload.

---

## 🔥 Aggiornamento prioritario – 9/10 novembre 2026

**Attribuzione ufficiale francese a Shahid Kaveh (IRGC-CEC)** per il sabotaggio dei sistemi di refrigerazione di ~700 siti commerciali in Francia (11–12 ottobre 2026).

| Documento | Contenuto |
|-----------|-----------|
| [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) | **Leadership dossier completo** (Hamid Reza Lashgarian, Mahdi Lashgarian, Reza Salarvand) + contesto ufficiale |
| [`campaigns/france-refrigeration-2026.md`](campaigns/france-refrigeration-2026.md) | Sintesi della campagna + basi di attribuzione pubbliche |
| [`groups/cyberav3ngers.md`](groups/cyberav3ngers.md) | Persona pubblica / front collegata a Shahid Kaveh |

Tutte le informazioni su nomi, ruoli e attribuzione derivano **esclusivamente** da dichiarazioni ufficiali francesi (Parquet de Paris, CERT-FR/C4, MFA) e reporting pubblico conseguente.

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
3. **Correlazione geopolitica 2026** — pre-posizionamento, downtime selettivi, resilienza sotto conflitto  
4. **Checklist operative con esempi** — domande e passi concreti per IR e hunting  
5. **Prospettive poco enfatizzate** — eterogeneità tra cluster, peso del pre-posizionamento, bias di visibilità, fragilità attributiva in crisi  

Tutto ancorato a advisory e report pubblici (CISA/FBI, CERT-FR, Semperis, ESET, Unit 42, ecc.).

---

## Navigazione rapida

### Per chi indaga ora
| Documento | Contenuto |
|-----------|-----------|
| [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) | Leadership IRGC-CEC / Shahid Kaveh (attribuzione francese 9 Nov 2026) |
| [`campaigns/france-refrigeration-2026.md`](campaigns/france-refrigeration-2026.md) | Campagna sabotaggio refrigerazione Francia |
| [`analysis/investigative-questions-checklist.md`](analysis/investigative-questions-checklist.md) | Domande + checklist + mini-playbook |
| [`analysis/investigative-priorities.md`](analysis/investigative-priorities.md) | Segnali prioritari (RMM, edge, OT) |

### Profili attori principali
| Gruppo | Note | Path |
|--------|------|------|
| **Shahid Kaveh** | Unità offensiva IRGC-CEC – attribuzione francese ufficiale | [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) |
| CyberAv3ngers | Persona / front OT-PLC collegata a Shahid Kaveh | [`groups/cyberav3ngers.md`](groups/cyberav3ngers.md) |
| MuddyWater | RMM, Starlink, possibile MaaS | [`groups/muddywater.md`](groups/muddywater.md) |
| Fox Kitten | Access broker + ransomware affiliates | [`groups/fox-kitten.md`](groups/fox-kitten.md) |
| Prince of Persia | Caso infrastrutturale 2026 | [`groups/prince-of-persia.md`](groups/prince-of-persia.md) |
| APT35 / APT34 / APT33 / others | Profili di base | `groups/` |

### Analisi di profondità
| Documento | Contenuto |
|-----------|-----------|
| [`analysis/geopolitical-cyber-correlation-2026.md`](analysis/geopolitical-cyber-correlation-2026.md) | Timeline cinetico–cyber 2026 |
| [`analysis/prince-of-persia-detailed.md`](analysis/prince-of-persia-detailed.md) | Caso C2 su shared hosting |
| [`analysis/starlink-iranian-actors.md`](analysis/starlink-iranian-actors.md) | Starlink come C2 e lure |
| [`analysis/what-is-missing-2026.md`](analysis/what-is-missing-2026.md) | Gap nelle narrazioni pubbliche |

---

## Struttura del repository

```
iranian-apt-osint/
├── README.md
├── methodology.md
├── groups/                   ← profili attori (incluso Shahid Kaveh)
├── campaigns/                ← campagne specifiche (Francia 2026)
├── iocs/                     ← indicatori pubblici contestualizzati
├── analysis/                 ← geopolitica, gap, checklist, Starlink
└── infrastructure/
```

---

## Metodologia e disclaimer fonti

**Tutte le informazioni contenute in questo repository (nomi, IP, domini, attribuzioni, TTPs) derivano esclusivamente da fonti pubbliche verificate.**

- Fonti primaria: advisory governative (CERT-FR, CISA, FBI, Treasury OFAC, MFA francesi)
- Fonti secondarie: report tecnici di vendor e media che riportano le dichiarazioni ufficiali
- Nessun dato classificato, nessuna informazione non pubblica, nessuna invenzione

Dettaglio completo: [`methodology.md`](methodology.md)

---

## Status

**Ultimo aggiornamento:** 10 novembre 2026  

Incluso:  
- Dossier leadership Shahid Kaveh (attribuzione ufficiale francese)  
- Campagna sabotaggio refrigerazione Francia ottobre 2026  
- Profili chiave, correlazione geopolitica, checklist IR, analisi gap  

---

*Independent OSINT research · Defensive and investigative reference only · Public sources only*
