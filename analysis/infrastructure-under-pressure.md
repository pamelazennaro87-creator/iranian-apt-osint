# Infrastructure under pressure

**Progetto OSINT distintivo del repository.**  
Oggetto: come i cluster cyber allineati all’Iran cambiano (o non cambiano) infrastruttura di C2, hosting e canali sotto stress geopolitico e sotto ricerca pubblica — 2025–2026.

Non è una collezione di gruppi. È un **metodo su infrastruttura + tempo**.

---

## Domanda di ricerca

Quando aumenta la pressione (conflitto cinetico, blackout, advisory, report vendor), cosa succede all’infrastruttura degli attori iraniani?

- Si spengono?
- Migrano (VPS → shared, Europa → USA, pannello X → Y)?
- Diversificano i canali (Starlink, Telegram, RMM, Cloudflare)?
- Quanto è veloce la reazione alla ricerca pubblica?
- Quali pattern restano stabili e quindi cacciabili?

---

## Ambito (in / out)

**In scope**
- Hosting e ASN (VPS dedicati, shared hosting, CDN)
- Domini, DGA, certificati SSL, pannelli di gestione (Cyber Panel, cPanel, ecc.)
- Canali C2 non tradizionali (Telegram API, Starlink/ASN satellitari, RMM commerciali)
- Timing rispetto a: report pubblici, blackout Iran, finestre di conflitto 2026
- Solo fonti e indicatori già pubblici

**Out of scope**
- Malware reverse approfondito (salvo quanto serve a capire il C2)
- Attribuzione a persone fisiche
- IOC non pubblici / dati vittima
- Claim hacktivist senza riscontro infrastrutturale

---

## Casi ancora da trattare come pilastri

| Caso | Perché conta | Stato nel repo |
|------|----------------|----------------|
| Prince of Persia → Namecheap shared (USA), cPanel, poi Cloudflare | Camuffamento ambientale sotto/dopo conflitto | Dettagliato |
| MuddyWater / Handala + Starlink in blackout | Canale non terrestre come resilienza | Parziale |
| Burst infrastruttura pre-feb 2026 (CIDR / staging) | Staging vs reazione | Da approfondire |
| Range europei storici PoP (`45.80.x`) vs post-migrazione | Continuità vs rottura | Parziale |
| RMM come “infra senza infra” | C2 che non sembra C2 | In profili, da legare al metodo |

---

## Deliverable del progetto (massimo 4)

1. **Metodo** — come si osserva una migrazione infrastrutturale da fonti aperte (passi, fonti, limiti)  
2. **Schede caso** — una per pilastro (PoP 2026 già avviata; Starlink; pre-positioning infra; RMM-as-C2)  
3. **Segnali cacciabili** — lista corta di comportamenti/ASN/pattern utili a hunting, non dump di IP  
4. **Checklist IR** — già avviata; da tenere allineata ai soli pattern infrastrutturali solidi  

Tutto il resto (profili attori, geopolitica) resta di supporto, non il centro.

---

## Regole anti-errore

- Correlazione temporale ≠ causalità: si documenta il timing, non si inventa l’ordine del committente  
- Shared hosting: l’IP da solo non attribuisce  
- Starlink: discrimina host fissi non autorizzati, non “qualsiasi IP SpaceX”  
- Ogni scheda caso chiude con: cosa è solido / cosa è ipotesi / cosa non si sa  

---

## Prossimi passi operativi

1. Chiudere la scheda metodo (passi riproducibili).  
2. Completare scheda Starlink in chiave *solo infrastruttura* (ASN, timing blackout, limiti GeoIP).  
3. Estrarre dal caso PoP una lista di **segnali di migrazione** riusabili su altri cluster.  
4. Una passata pubblica su burst pre-feb 2026 (solo ciò che è già in report) senza allargare il perimetro.  

---

## Collegamenti

- `analysis/prince-of-persia-detailed.md`  
- `iocs/prince-of-persia-2026.md`  
- `analysis/starlink-iranian-actors.md` / `starlink-hunting-notes.md`  
- `analysis/geopolitical-cyber-correlation-2026.md`  
- `analysis/investigative-questions-checklist.md`  
- `analysis/aggressive-research-agenda.md`  

---

*Flagship angle del repository: infrastruttura sotto pressione, non enciclopedia APT.*
