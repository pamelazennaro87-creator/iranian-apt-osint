# Correlazione geopolitica–cyber 2026

**Ambito:** interazione tra eventi cinetici USA/Israele–Iran (febbraio–giugno 2026) e comportamento dei cluster APT iraniani, con focus su Prince of Persia, MuddyWater, APT34 e attività OT/ICS.  
**Fonti:** Semperis, Unit 42, advisories congiunti USA, reporting di threat intelligence multiplo.

---

## 1. Timeline integrata (cinetico + cyber)

| Data | Evento geopolitico / cinetico | Attività cyber osservata |
|------|-------------------------------|---------------------------|
| Gen 2026 | Blackout internet Iran (8 gen); tensioni crescenti | MuddyWater: Operation Olalampo (da ~26 gen) con nuove famiglie Rust; uso di Starlink per resilienza C2 durante blackout |
| Inizio feb 2026 | Colloqui e segnali di tensione (chiusura temporanea Stretto di Hormuz come leva) | **Pre-posizionamento:** MuddyWater e APT34 rilevati su reti USA (difesa, banking, aeroporti). Pay2Key su healthcare USA a fine febbraio |
| 4–9 feb 2026 | — | Prince of Persia: reazione a ricerca SafeBreach → spegnimento e rebuild rapido C2 |
| **28 feb 2026** | **Inizio Operation Epic Fury / Roaring Lion:** attacchi aerei USA/Israele su infrastrutture missilistiche, militari e leadership iraniana | Blackout internet Iran; Prince of Persia entra nel downtime più lungo della sua storia (~3 mesi). Altri cluster mostrano disruption ma non scomparsa |
| 1–10 mar 2026 | Ritorsioni iraniane (missili/droni su basi USA regionali e traffico marittimo) | Attività cyber di ritorsione attesa e in parte osservata (wiper, claim hacktivist, pressione su CI). Advisory urgenti su PLC/OT |
| Apr 2026 | Ceasefire breve (8 apr); blocco navale USA (12–13 apr) | AA26-097A (7 apr): warning su disruption di PLC Rockwell Allen-Bradley da parte di attori iraniani (da almeno marzo). Continuazione di attività OT |
| Mag 2026 | — | Prince of Persia riprende (27 mag): nuovo C2, exfiltration intensa |
| Giu 2026 | MoU USA–Iran (17 giu) | Stabilizzazione relativa; Prince of Persia costruisce C2 Tornado su shared hosting Namecheap USA (~lug) |
| Lug–Ago 2026 | Post-accordo | Scoperta del C2 USA di Prince of Persia; migrazione parziale dietro Cloudflare |

---

## 2. Pattern di correlazione

### A. Pre-posizionamento prima del trigger cinetico
Fonti multiple indicano che cluster MOIS (MuddyWater) e OilRig/APT34 avevano già implant su reti USA di interesse (difesa, finance, aeroporti, healthcare) **nelle settimane precedenti** il 28 febbraio.  
Questo è coerente con comportamento di **preparazione a opzioni cyber** piuttosto che sola reazione post-strike.

### B. Downtime selettivo vs resilienza
- **Prince of Persia:** downtime prolungato e storico. Coerente con dipendenza da infrastruttura e operatori più vulnerabili a disruption interna o a blackout.
- **MuddyWater e altri:** mostrano maggiore resilienza (Starlink, infrastruttura estera, possibile pre-posizionamento). I blackout domestici non fermano chi ha già accesso e canali alternativi.
- **IRGC-linked (CyberAv3ngers / OT):** attività su PLC documentata almeno da marzo, in piena fase di ostilità → priorità su effetti distruttivi/disruptive su infrastrutture critiche.

### C. Cyber come strumento di ritorsione asimmetrica
Con le capacità convenzionali degradate dagli strike, il cyber diventa uno dei pochi strumenti di risposta asimmetrica disponibili.  
Le valutazioni di febbraio–marzo 2026 ponevano come scenari ad alta probabilità: wiper su CI israeliane/USA, pressione OT/ICS, campagne di claim e hacktivism a supporto narrativo.

### D. Scelta del C2 USA da parte di Prince of Persia
Il posizionamento del C2 Tornado su shared hosting Namecheap **negli Stati Uniti** avviene nel contesto del conflitto e della successiva fase di accordo.  
Interpretazioni possibili (non mutuamente esclusive):
- Necessità di opacità massima dopo la disruption europea/precedente.
- Calcolo che il rumore del shared hosting USA riduca la probabilità di takedown rapido.
- Segnale involontario di pressione sulle opzioni infrastrutturali tradizionali.

---

## 3. Implicazioni per analisi e indagini

1. **Le finestre pre-cinetiche contano**  
   L’attività di pre-posizionamento (febbraio) è un indicatore di intento e di priorità di targeting più forte di molti claim post-evento.

2. **Non tutti i cluster reagiscono allo stesso modo**  
   Prince of Persia (più “classico”, infrastruttura più esposta) vs MuddyWater (RMM + Starlink + possibile MaaS) vs attori OT IRGC. La risposta al conflitto è eterogenea e rivela differenze di maturità e di dipendenza da infrastruttura domestica.

3. **Blackout ≠ incapacità**  
   Gli operatori con C2 estero, Starlink o implant già presenti restano operativi. Il blackout colpisce soprattutto chi dipende dalla connettività iraniana in tempo reale.

4. **OT/ICS come priorità di ritorsione**  
   L’advisory AA26-097A e l’attività su PLC Rockwell in piena fase di ostilità confermano che gli effetti su processi fisici restano un obiettivo di alto valore.

5. **Utilità predittiva**  
   Periodi di escalation geopolitica tendono a produrre:
   - aumento di pre-posizionamento e scanning;
   - downtime di alcuni cluster;
   - picchi di attività disruptive/wiper e di claim hacktivist;
   - possibili migrazioni infrastrutturali (come il caso Namecheap).

---

## 4. Collegamenti con gli altri angoli del repository

- **Starlink:** usato proprio per mantenere C2 durante blackout (MuddyWater e altri). La geopolitica rende il canale satellitare non solo tecnico ma strategico.
- **Shared hosting USA (Prince of Persia):** scelta presa nel contesto del conflitto e della successiva ricerca di opacità.
- **Fox Kitten / access broker:** in fase di tensione il valore degli accessi già ottenuti aumenta (possibile uso duale spionaggio + pressione).
- **RMM e living-off-the-land:** meno dipendenti da infrastruttura C2 “pesante” e quindi più resilienti ai blackout.

---

## 5. Limiti

- Correlazione temporale non equivale a causalità diretta in ogni singolo caso.
- Parte dell’attività resta sotto-riportata o attribuita solo a livello di cluster ampio.
- I claim hacktivist in fase di conflitto hanno spesso basso valore evidenziale e alto valore narrativo.

---

*Documento di sintesi investigativa. Da usare insieme alle timeline dei singoli cluster e agli IOC pubblici già raccolti nel repository.*
