# Domande investigative e checklist operativa

Derivate da `what-is-missing-2026.md` e dalla correlazione geopolitica–cyber.  
Obiettivo: trasformare le lacune analitiche in domande e controlli utilizzabili da investigatori e difensori.

---

## A. Domande da porsi su ogni incidente sospetto (priorità)

### 1. Tempistica rispetto agli eventi geopolitici
- L’accesso iniziale o il beacon osservato è **prima**, **durante** o **dopo** una finestra di escalation nota (es. pre-28 feb 2026, blackout, ceasefire)?
- Esiste attività di scanning o di infrastruttura nuova nei 30–90 giorni precedenti il trigger cinetico?

### 2. Quale “tipo” di attore sembra coerente?
- L’attività assomiglia di più a:
  - **intrusione lunga / spionaggio / RMM** (profilo più MOIS-like),
  - **effetto OT/PLC / defacement / persona rumorosa** (profilo più IRGC-like),
  - **access broker + possibile hand-off ransomware** (Fox Kitten-like),
  - **spionaggio su dissidenti / targeting mirato a basso volume** (Prince of Persia-like)?
- Evitare di chiudere subito su “Iranian APT” senza discriminare.

### 3. Resilienza di canale
- Ci sono indicatori di C2 non tradizionale (egress verso range/ASN satellitari, RMM commerciali, canali Telegram, shared hosting multi-tenant)?
- L’attività è proseguita durante blackout o restrizioni di connettività iraniane note?

### 4. Qualità dell’accesso vs rumore
- Si tratta di accesso silenzioso e persistente, o di attività rumorosa (defacement, claim, wiper visibile)?
- In presenza di claim pubblici: esiste evidenza tecnica indipendente, o solo narrazione?

### 5. Possibile dual-use o hand-off
- L’accesso potrebbe essere utile sia a fini di intelligence sia a fini criminali/ransomware?
- Ci sono tracce di edge exploitation (VPN/appliance) coerenti con access brokerage?

---

## B. Checklist per indagini su reti USA / alleate (contesto 2026)

**Pre-posizionamento e persistenza**
- [ ] Verificare log di autenticazione e EDR per attività anomala nelle settimane precedenti finestre di escalation note
- [ ] Cercare RMM non autorizzati (Atera, ScreenConnect, Syncro, PDQ, SimpleHelp, Level, ecc.) e inventariare tenant ID
- [ ] Controllare implant o backdoor già documentati su settori sensibili (difesa, finance, aeroporti, healthcare, energy)

**Canali e infrastruttura**
- [ ] Includere in hunting gli ASN/range di uplink satellitare (Starlink/SpaceX) per host non autorizzati
- [ ] Correlare traffico verso shared hosting Namecheap / cPanel con domini sospetti o DGA
- [ ] Monitorare uso anomalo di API Telegram da host aziendali

**OT / ICS**
- [ ] Verificare esposizione internet di PLC (Rockwell, Schneider, Siemens, Unitronics) e credenziali di default
- [ ] Controllare modifiche a HMI, logica di shutdown/allarmi, e accessi engineering da fonti non attese
- [ ] Allineare eventuali eventi OT alla timeline AA26-097A e successive

**Attribuzione e bias**
- [ ] Non basare l’attribuzione su un singolo IP, dominio o claim
- [ ] Documentare esplicitamente incertezze (possibile riuso di infrastruttura, tooling condiviso, MaaS)
- [ ] Separare evidenza tecnica da narrazione di personas/hacktivist

---

## C. Domande specifiche per cluster (quando i segnali puntano in una direzione)

**Se emergono segnali MuddyWater-like**
- C’è overlap temporale o di vittima con OilRig/Lyceum?
- Sono presenti certificati di code-signing o builder che appaiono anche in ecosistemi MaaS criminali?
- L’egress passa da canali satellitari o RMM in periodi di blackout?

**Se emergono segnali Fox Kitten-like**
- L’accesso iniziale è su edge device (Citrix, Ivanti, F5, PAN-OS, Check Point)?
- Esistono webshell in path non standard o tunneling residuo dopo il patching?
- L’incidente ha o potrebbe avere un seguito ransomware con affiliate noti (ALPHV, NoEscape, RansomHouse)?

**Se emergono segnali Prince of Persia-like**
- Ci sono domini `*.privatedns.org` o pattern DGA coerenti?
- Traffico Telegram bot / exfiltration con formato file particolare?
- Infrastruttura su shared hosting (Namecheap) + cPanel invece che VPS dedicato?

**Se emergono segnali OT / CyberAv3ngers-like**
- PLC esposti, default password, porte OT raggiungibili dall’esterno?
- Modifiche a display HMI o disabilitazione di logiche di sicurezza?
- Coerenza con IP/range e finestre già pubblicati in AA26-097A / AA23-335A?

---

## D. Domande di secondo livello (per team di analisi)

1. Stiamo pesando i claim pubblici più dell’evidenza di accesso silenzioso?
2. Stiamo trattando tutti i cluster iraniani come se avessero la stessa resilienza e la stessa missione?
3. Abbiamo considerato esplicitamente il bias di visibilità (molto reporting in uscita, poco su effetti interni all’Iran)?
4. In presenza di fingerprint “iraniani”, abbiamo escluso quanto possibile scenari di riuso/hijacking di infrastruttura (monito metodologico Turla–OilRig)?
5. Le nostre watchlist e i playbook di GeoIP/ASN sono aggiornati a canali satellitari e shared hosting multi-tenant?

---

## E. Uso consigliato

- **Incident response:** sezioni A + B come checklist di primo passaggio.  
- **Threat hunting proattivo:** sezione B + domande di cluster (C) in base ai segnali.  
- **Analisi strategica / briefing:** sezione D per evitare conclusioni troppo aggregate.

---

*Allineato a fonti pubbliche e alle analisi già presenti nel repository. Non sostituisce procedure interne di LE o di SOC.*
