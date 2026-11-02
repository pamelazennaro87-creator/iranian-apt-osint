# Starlink e attori iraniani – Indagine aggressiva

**Stato:** analisi basata su fonti pubbliche ad alta e media confidenza.  
Obiettivo: mappare l’uso duale di Starlink da parte di cluster iraniani e le implicazioni investigative.

---

## 1. Uso confermato di Starlink come canale C2

### MuddyWater (MOIS)
- **Fonte primaria:** MITRE ATT&CK G0069 e profili derivati (aggiornati 2026).
- **Periodo:** fine 2025 – inizio 2026.
- **Descrizione:** uso di internet satellitare commerciale (esplicitamente Starlink) per command and control.
- **Contesto operativo:** coincide con campagne ad alta intensità (Phoenix, MuddyViper, onde energy/maritime) e con periodi di tensione/blackout in Iran.

### Handala (persona MOIS-linked / hacktivist-styled)
- **Fonte:** Check Point (riportato da Forbes, marzo 2026).
- **Periodo:** almeno da metà gennaio 2026 fino a fine febbraio 2026 (e probabilmente oltre).
- **Descrizione:** il gruppo ha usato Starlink per rimanere operativo durante i blackout internet imposti dal regime iraniano.
- **Nota:** Handala è frequentemente descritto come operato o diretto da elementi MOIS sotto copertura “hacktivist”.

**Sintesi:** almeno due cluster legati al MOIS hanno usato Starlink come canale di comunicazione operativa. Non risulta (ancora) evidenza pubblica equivalente altrettanto chiara per cluster IRGC-CEC puri (CyberAv3ngers, ecc.), ma l’assenza di reporting non equivale ad assenza di uso.

---

## 2. Uso di “Starlink” come lure contro la popolazione iraniana

### DCHSpy / Earth VPN (attribuito a MuddyWater)
- **Fonte:** Lookout (2025).
- **Tattica:** distribuzione di spyware Android mascherato da app/VPN legata a Starlink (es. filename `starlink_vpn...apk`).
- **Target:** utenti iraniani alla ricerca di internet non filtrato.
- **Canale di distribuzione:** principalmente Telegram e messaging app.

**Paradosso operativo:**  
Lo stesso ecosistema (MuddyWater) che usa Starlink per il proprio C2 sfrutta il desiderio di Starlink della popolazione iraniana come vettore di compromissione.  
Questo è un caso chiaro di **uso duale interno**: il brand e la tecnologia servono sia l’operatore che la vittima domestica.

---

## 3. La risposta del regime iraniano a Starlink

Fonti pubbliche (2025–2026) mostrano una postura aggressiva e multi-strato:

| Misura | Descrizione pubblica | Fonte tipo |
|--------|----------------------|----------|
| Criminalizzazione | Uso, possesso, importazione e distribuzione di terminali Starlink puniti con carcere (fino a 2 anni uso personale; pene più alte per distribuzione) | Legislazione 2025 + reporting |
| Sequestri | Operazioni IRGC e forze di sicurezza con recupero di decine di terminali + armi in alcuni casi | IRNA / reporting di stato |
| Jamming / disruption | Funzionari (Aghamiri, Consiglio Supremo dello Spazio Cibernetico) affermano di aver disabilitato terminali “in modo controllato” durante proteste e di avere sistemi di localizzazione e interferenza | Dichiarazioni ufficiali ott 2026 |
| GPS spoofing | Analisi tecniche di telemetria Starlink da Iran mostrano spoofing GPS con perdita di pacchetti elevata e connessioni instabili | Reporting tecnico gen 2026 |
| Stima utenti | Decine di migliaia di terminali operativi in Iran nonostante il divieto (stime 30k–50k+ a seconda della fonte) | Organizzazioni di diritti e reporting |

**Implicazione:** il regime tratta Starlink contemporaneamente come:
- Minaccia di sovranità e strumento di “nemici”.
- Tecnologia che i propri operatori di intelligence usano quando serve (soprattutto in condizioni di blackout o per resilienza C2).

---

## 4. Angoli divergenti e domande ad alto valore investigativo

### A. Attribution e detection di C2 satellitare
- Il traffico Starlink non ha la stessa geolocalizzazione IP “classica”. Gli IP di uscita possono apparire in range SpaceX / gateway satellitari.
- Domanda: esistono fingerprint di beacon (intervalli, protocolli, user-agent, certificate) che distinguano il C2 MuddyWater via Starlink da traffico legittimo Starlink?
- Possibile pivot: correlare attività C2 note di MuddyWater con periodi di blackout internet in Iran o con picchi di traffico satellitare.

### B. Supply chain dei terminali usati dagli operatori
- I terminali usati da MuddyWater/Handala sono gli stessi smuggling network che riforniscono attivisti e popolazione?
- Oppure esistono canali di approvvigionamento separati (più professionali, meno esposti a sequestro)?
- Un terminale sequestrato in operazioni IRGC potrebbe, in teoria, contenere artefatti utili se era stato usato anche per C2.

### C. Starlink come indicatore di resilienza operativa
- L’adozione di Starlink da parte di cluster MOIS suggerisce preparazione a operare sotto blackout o sotto pressione sulle infrastrutture terrestri iraniane.
- È un segnale di maturità operativa: non dipendere solo dalla connettività domestica o da VPS esteri tradizionali.

### D. Rischio di false flag / confusione
- Poiché anche attori non iraniani (e forze in altri teatri) usano Starlink, la sola presenza di traffico satellitare non è attributiva.
- Serve sempre correlazione con tooling, timing, targeting e infrastruttura tradizionale.

---

## 5. Sintesi operativa per investigatori

| Elemento | Valore investigativo | Note |
|----------|----------------------|------|
| Uso C2 Starlink da MuddyWater | Alto | Periodo fine 2025–inizio 2026; confermato da fonti multiple |
| Uso C2 Starlink da Handala | Medio-Alto | Durante blackout; fonte Check Point |
| Lure “Starlink” per spyware | Alto | Dimostra conoscenza e sfruttamento del desiderio di connettività non filtrata |
| Misure repressive del regime | Contestuale | Aiuta a capire il costo e il rischio operativo per chi usa Starlink in Iran |
| IP/gateway Starlink in log | Medio | Da soli deboli; potenti in correlazione con altre IOCs o comportamenti |

**Raccomandazione:** in indagini su MuddyWater o cluster MOIS correlati, includere esplicitamente la ricerca di beacon o connessioni verso infrastruttura satellitare/SpaceX nei periodi rilevanti. Non trattare Starlink come canale “solo civile”.

---

## Fonti principali usate
- MITRE ATT&CK G0069 (MuddyWater – satellite internet C2)
- Check Point / Forbes (Handala + Starlink)
- Lookout (DCHSpy / Starlink lure)
- Dichiarazioni Consiglio Supremo dello Spazio Cibernetico iraniano (2026)
- Reporting tecnico su GPS spoofing e disruption
- Reporting su smuggling e stime di terminali in Iran

*Documento aggiornato: 2026-11-02. Destinato a uso investigativo e di ricerca difensiva.*
