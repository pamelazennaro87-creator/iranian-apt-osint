# Pattern di Navigazione Operativa – Cluster Iraniani

**Focus:** Come gli attori si muovono nell’infrastruttura, come trovano i target, come stabiliscono e mantengono le connessioni.  
Analisi basata esclusivamente su reporting pubblico (CISA, ESET, Unit 42, Censys, industria).

---

## 1. CyberAv3ngers / Attività PLC (IRGC-CEC)

### Pattern di ricognizione e accesso

| Fase | Comportamento osservato | Segnale investigativo |
|------|--------------------------|-----------------------|
| **Discovery** | Scanning/probing di porte OT specifiche su larga scala | Porte 44818 (EtherNet/IP), 2222, 502 (Modbus), 102 (S7), 20256 (Unitronics storico), 22 |
| **Selezione target** | Preferenza per dispositivi internet-esposti con banner riconoscibili e, storicamente, credenziali di default | Dispositivi con firmware end-of-sale o configurazioni deboli vengono prioritizzati |
| **Accesso iniziale** | Connessione diretta da VPS esteri usando software engineering legittimo del vendor (Studio 5000, FactoryTalk, poi anche tool Schneider/Siemens) | Traffico “da ingegnere” originato da range VPS atipici (es. cluster 185.82.73.x) |
| **Interazione** | Download di project file, modifica di logica/HMI, cambio password/IP per lock-out operatori, manipolazione dati visualizzati | Sessioni di engineering non autorizzate + cambiamenti non tracciati in change management |
| **Persistenza / C2** | Uso limitato di tool propri; preferenza per protocolli nativi OT e, in fasi successive, MQTT over TLS (IOCONTROL) | Traffico MQTT/TLS (8883) o DoH in contesti OT |

**Caratteristica distintiva:** non navigano “dentro” la rete vittima in modo tradizionale (poco lateral movement documentato). Navigano **sull’attack surface esterna** dei PLC. Il pattern è più “scan → connect as engineer → manipulate” che “phish → foothold → move laterally”.

### Pattern infrastrutturali degli operatori
- Workstation di engineering multi-homed (stesso host, più IP nel range 185.82.73.160–171).
- Staging box di breve durata (es. 135.136.1.133 attiva pochi giorni).
- RDP su porta non standard + certificati self-signed con hostname Windows riconoscibili.

---

## 2. MuddyWater (MOIS)

### Pattern di navigazione tipici

| Fase | Comportamento | Note |
|------|---------------|------|
| **Initial access** | Spear-phishing (spesso da mailbox già compromesse), documenti macro, a volte exploit di applicazioni esposte | Uso frequente di lures tematici (paghe, documenti ufficiali) |
| **Foothold** | Installazione di RMM legittimi (Atera, ScreenConnect, Syncro, PDQ, SimpleHelp, Level…) | Uno dei segnali comportamentali più forti e duraturi |
| **C2 / Navigazione post-compromissione** | Beacon HTTP/S (Phoenix e varianti), uso di Telegram Bot API in alcuni tool, tunneling (Ligolo), RMM come canale primario | Preferenza per tool che si mescolano al traffico legittimo |
| **Movimento laterale** | Credential dumping + tool legittimi/amministrativi (CrackMapExec, ecc.) | Più “enterprise” rispetto a CyberAv3ngers |
| **Evoluzione recente** | Sperimentazione di C2 via Starlink (fine 2025 – inizio 2026); shift verso tool compilati e Rust-based | Riduzione della dipendenza da PowerShell puro |

**Differenza chiave rispetto a CyberAv3ngers:** MuddyWater naviga **dentro** le reti vittima (enterprise + OT/telecom). CyberAv3ngers naviga principalmente **sull’edge esposto** dei controller industriali.

---

## 3. Pattern trasversali osservati

### A. Preferenza per strumenti legittimi
Entrambi i cluster (e altri attori iraniani) abusano pesantemente di software legittimo:
- RMM per MuddyWater
- Software engineering del vendor per CyberAv3ngers
Questo crea un pattern di “navigazione camuffata”: il traffico sembra autorizzato fino a che non si guarda la sorgente geografica/hosting o il contesto.

### B. Ricognizione a larga scala → pivot selettivo
- Scanning ampio di dispositivi esposti (migliaia di host).
- Selezione successiva dei target ad alto valore o più vulnerabili.
- Pattern osservato anche in campagne MuddyWater-style (scan di 12.000+ sistemi prima di attacchi mirati).

### C. Infrastruttura operatore a basso costo e ad alto turnover
- VPS esteri, Namecheap, hosting condiviso.
- Domini di breve vita.
- Raro uso di infrastruttura “pregiata” o long-lived.

### D. Accoppiamento propaganda–operazione (soprattutto CyberAv3ngers)
I claim pubblici e le defacement seguono da vicino le finestre di attività reale. Questo riduce la separazione tra navigazione tecnica e navigazione narrativa.

---

## 4. Implicazioni per detection e investigazione

| Segnale ad alto valore | Perché |
|------------------------|--------|
| Connessioni verso porte OT (44818, 502, 102, 20256, 2222) da range VPS esteri | Pattern di accesso CyberAv3ngers |
| Presenza di software engineering vendor da IP non aziendali / non attesi | Stesso cluster |
| Installazione o uso di RMM non approvati (Atera, ScreenConnect, ecc.) | MuddyWater e affini |
| Beacon HTTP periodici + tool RMM nello stesso ambiente | MuddyWater post-compromise |
| Traffico MQTT over TLS o DoH in segmenti OT | IOCONTROL / fasi avanzate |
| Overlap temporali o di vittima tra MuddyWater e OilRig/Lyceum | Possibile sharing di accessi |

---

## 5. Sintesi operativa

- **CyberAv3ngers** naviga sull’**edge industriale esposto**. Pattern dominante: scan di porte OT → connessione con tool legittimi da VPS → manipolazione.
- **MuddyWater** naviga **dentro** le reti. Pattern dominante: phishing/RMM → foothold → movimento laterale con tool misti legittimi/custom.
- Il punto in comune più utile per le forze dell’ordine e i difensori è l’abuso di strumenti legittimi da contesti anomali (geografia, hosting, assenza di change ticket).

---

*Documento basato su fonti pubbliche. Aggiornabile con nuove osservazioni ad alta confidenza.*
