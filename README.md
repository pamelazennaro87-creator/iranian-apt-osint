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
| [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) | **Leadership dossier completo** (Hamid Reza Lashgarian, Mahdi Lashgarian, Reza Salarvand) + identificatori pubblici OFAC + note tecniche CERT-FR |
| [`analysis/modus-operandi-and-investigative-leads.md`](analysis/modus-operandi-and-investigative-leads.md) | **Modus operandi + ricerca divergente**: TTPs, reclutamento, segnali duraturi e lead investigativi utili |
| [`campaigns/france-refrigeration-2026.md`](campaigns/france-refrigeration-2026.md) | Sintesi della campagna + basi di attribuzione e contesto tecnico |
| [`groups/cyberav3ngers.md`](groups/cyberav3ngers.md) | Persona pubblica / front collegata a Shahid Kaveh |
| [`SOURCES.md`](SOURCES.md) | Elenco completo delle fonti pubbliche utilizzate |

Tutte le informazioni derivano **esclusivamente** da dichiarazioni ufficiali francesi, listing OFAC e reporting pubblico.

---

## A chi serve

| Utente | Utilità |
|--------|--------|
| Investigatori / forze dell’ordine | Orientamento rapido, discriminanti tra cluster, checklist IR, lead investigativi |
| SOC / detection engineering | Segnali comportamentali duraturi (engineering software da VPS, porte OT, FOFA) |
| Analisti CTI / ricercatori OSINT | Sintesi strutturata + angoli divergenti ancora sfruttabili |

**Non è:** intelligence classificata, feed di IOC da “block & forget”, né prova giudiziaria autonoma.

---

## Navigazione rapida

### Per chi indaga ora
| Documento | Contenuto |
|-----------|-----------|
| [`analysis/modus-operandi-and-investigative-leads.md`](analysis/modus-operandi-and-investigative-leads.md) | **TTPs + lead investigativi + OPSEC residuals** |
| [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) | Leadership IRGC-CEC / Shahid Kaveh |
| [`campaigns/france-refrigeration-2026.md`](campaigns/france-refrigeration-2026.md) | Campagna sabotaggio refrigerazione Francia |
| [`SOURCES.md`](SOURCES.md) | Fonti primarie e secondarie complete |

### Profili attori principali
| Gruppo | Note | Path |
|--------|------|------|
| **Shahid Kaveh** | Unità offensiva IRGC-CEC – attribuzione francese ufficiale | [`groups/shahid-kaveh.md`](groups/shahid-kaveh.md) |
| CyberAv3ngers | Persona / front OT-PLC collegata a Shahid Kaveh | [`groups/cyberav3ngers.md`](groups/cyberav3ngers.md) |
| MuddyWater | RMM, Starlink, possibile MaaS | [`groups/muddywater.md`](groups/muddywater.md) |
| Fox Kitten | Access broker + ransomware affiliates | [`groups/fox-kitten.md`](groups/fox-kitten.md) |
| Prince of Persia | Caso infrastrutturale 2026 | [`groups/prince-of-persia.md`](groups/prince-of-persia.md) |

---

## Struttura del repository

```
iranian-apt-osint/
├── README.md
├── SOURCES.md
├── methodology.md
├── groups/                   ← profili attori (incluso Shahid Kaveh)
├── campaigns/                ← campagne specifiche (Francia 2026)
├── iocs/                     ← indicatori pubblici contestualizzati
├── analysis/                 ← geopolitica, gap, checklist, Starlink, **modus operandi & leads**
└── infrastructure/
```

---

## Metodologia e disclaimer fonti

**Tutte le informazioni contenute in questo repository derivano esclusivamente da fonti pubbliche verificate.**

Dettaglio completo: [`methodology.md`](methodology.md) e [`SOURCES.md`](SOURCES.md)

---

## Status

**Ultimo aggiornamento:** 10 novembre 2026  

Incluso:  
- Dossier leadership Shahid Kaveh completo  
- **Analisi modus operandi + ricerca divergente e lead investigativi**  
- Campagna sabotaggio refrigerazione Francia  
- Elenco fonti strutturato  

---

*Independent OSINT research · Defensive and investigative reference only · Public sources only*
