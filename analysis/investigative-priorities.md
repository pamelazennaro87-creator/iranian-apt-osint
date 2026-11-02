# Segnali prioritari per indagini e difesa

Documento operativo sintetico. Ordine di priorità basato su valore investigativo e durabilità del segnale.

---

## Priorità Alta

| Segnale | Cluster principale | Perché è utile |
|---------|--------------------|----------------|
| RMM non autorizzati (Atera, ScreenConnect, Syncro, PDQ, SimpleHelp, Level…) | MuddyWater | Foothold preferito e persistente; tenant ID e agent sono identità tracciabili |
| Software engineering vendor (Studio 5000, FactoryTalk, EcoStruxure, TIA Portal) da VPS/hosting estero | CyberAv3ngers / AA26-097A | Pattern di accesso “da ingegnere” illegittimo; cluster IP 185.82.73.x storicamente associato |
| Compromissione di edge device (Citrix, Ivanti, F5, PAN-OS, Check Point) seguita da webshell in path non standard o tunneling | Fox Kitten | Possibile upstream di ransomware (ALPHV, NoEscape, RansomHouse) o di spionaggio |
| Overlap temporali o di vittima tra MuddyWater e OilRig/Lyceum | MuddyWater ↔ OilRig | Indicatore di possibile sharing di accessi iniziali |
| Traffico verso porte OT (44818, 2222, 502, 102, 20256) da range VPS non attesi | CyberAv3ngers | Ricognizione e accesso su PLC esposti |

---

## Priorità Media

| Segnale | Note |
|---------|------|
| Beacon HTTP periodici + presenza di RMM nello stesso ambiente | MuddyWater post-compromise |
| MQTT over TLS (porta 8883) o DoH in segmenti OT | IOCONTROL / fasi avanzate CyberAv3ngers |
| Domini Namecheap di breve vita + infrastruttura a basso costo | Pattern trasversale multi-cluster |
| Claim pubblici di defacement o disruption che coincidono con finestre di attività reale | CyberAv3ngers persona management |
| Uso di Starlink o canali satellitari per C2 | MuddyWater (2025–2026) |

---

## Priorità Contestuale (dipende dal caso)

- IP pubblici già pubblicati in AA26-097A e AA24-241A → utili per hunting storico, non come unico criterio di blocco.
- Hash e famiglie malware (Phoenix, MuddyViper, Tornado, IOCONTROL, ecc.) → utili quando si dispone di campioni o telemetria EDR.
- Persona e messaggistica Telegram → utili per timing e intent, meno per attribution tecnica dura.

---

## Domande investigative utili

1. L’accesso iniziale è avvenuto tramite edge device vulnerabile o tramite phishing/RMM?
2. Esistono webshell o tunnel residui anche dopo il patching?
3. Ci sono evidenze di accesso condiviso o di handover verso altri attori (ransomware o cluster iraniani diversi)?
4. Il traffico di engineering o RMM proviene da geografie/hosting coerenti con l’organizzazione vittima?
5. Esistono overlap temporali con altre campagne note dello stesso ecosistema?

---

*Questo elenco privilegia segnali comportamentali e di contesto rispetto a IOC statici a breve vita. Aggiornabile con nuove osservazioni ad alta confidenza.*
