# Domande investigative e checklist operativa (con esempi pratici)

Derivate da `what-is-missing-2026.md` e dalla correlazione geopolitica–cyber.  
Obiettivo: domande e controlli immediatamente utilizzabili, con esempi concreti legati a casi pubblici 2025–2026.

---

## A. Domande da porsi su ogni incidente sospetto

### 1. Tempistica rispetto agli eventi geopolitici

**Domande**
- L’accesso iniziale o il beacon è **prima**, **durante** o **dopo** una finestra di escalation nota?
- C’è scanning o nuova infrastruttura nei 30–90 giorni precedenti il trigger cinetico?

**Esempi pratici**
- Beacon o login anomali su rete USA tra **inizio febbraio e 27 febbraio 2026** → prioritizzare come possibile pre-posizionamento (coerente con reporting su MuddyWater/APT34), non come sola reazione post-strike.
- Nuova infrastruttura C2 registrata a **settembre 2025 o gennaio 2026** e poi usata dopo il 28 febbraio → valutare come staging, non come improvvisazione.
- Attività che **scompare** tra fine febbraio e maggio 2026 e poi riparte → confrontare con il pattern Prince of Persia (downtime lungo sotto conflitto).

---

### 2. Quale “tipo” di attore sembra coerente?

**Domande**
- L’attività assomiglia di più a intrusione lunga/RMM, effetto OT, access broker, o targeting mirato a basso volume?

**Esempi pratici**
| Segnale osservato | Orientamento iniziale |
|-------------------|------------------------|
| Agent Atera/ScreenConnect non autorizzato + phishing da mailbox già compromessa | MuddyWater-like (MOIS) |
| Exploit su Citrix/Ivanti/F5 + webshell in path tipo `/var/vpn/themes/` + poi ransomware | Fox Kitten-like |
| PLC Rockwell/Unitronics esposto, default password, HMI alterato, claim Telegram | OT / CyberAv3ngers-like (IRGC-CEC) |
| Pochi target, exfiltration prolungata, domini DGA + Telegram bot, shared hosting | Prince of Persia-like |
| Solo defacement o claim senza evidenza tecnica | Persona/hacktivist — basso peso attributivo finché non c’è telemetria |

---

### 3. Resilienza di canale

**Domande**
- Ci sono C2 non tradizionali (satellitare, RMM, Telegram, shared hosting)?
- L’attività è proseguita durante blackout iraniani noti?

**Esempi pratici**
- Host fisso di ufficio (non laptop mobile) che fa egress verso **ASN SpaceX/Starlink** a gennaio o fine febbraio 2026 → investigare come possibile C2 satellitare (pattern documentato per MuddyWater/Handala in blackout).
- Connessioni periodiche verso IP **Namecheap shared** (es. range legati a `68.65.122.203` / AS22612) + domini `*.privatedns.org` → confrontare con caso Tornado/Prince of Persia.
- Processo `ScreenConnect` o `AteraAgent` che parla con tenant non aziendali durante un periodo di blackout in Iran → segnale di resilienza tipico RMM-based, non di C2 “classico” da VPS.

---

### 4. Qualità dell’accesso vs rumore

**Domande**
- Accesso silenzioso e persistente, o attività rumorosa?
- I claim pubblici hanno evidenza tecnica indipendente?

**Esempi pratici**
- **Alto valore:** backdoor confermata da EDR/Unit 42 su rete bancaria o aeroportuale a fine febbraio, senza claim pubblici → pre-posizionamento.
- **Basso valore isolato:** canale Telegram che rivendica “abbiamo preso il PLC della città X” senza log, dump o conferma da parte della vittima → trattare come narrazione finché non c’è telemetria.
- **Misto:** claim di defacement + modifica reale a HMI su PLC esposto → il claim è rumoroso, ma l’effetto OT è verificabile e va investigato a parte.

---

### 5. Possibile dual-use o hand-off

**Domande**
- L’accesso serve intelligence, ransomware, o entrambi?
- Ci sono tracce di edge exploitation tipiche di access brokerage?

**Esempi pratici**
- Compromissione iniziale via **CVE su VPN** (Citrix NetScaler, Ivanti, PAN-OS, Check Point) seguita da tunneling (Ligolo, socat) e poi da affiliate ransomware noti (ALPHV, NoEscape, RansomHouse) → pattern Fox Kitten documentato in AA24-241A.
- Stesso accesso usato prima per collection e poi per encryption → non chiudere l’indagine come “solo ransomware”; documentare la fase upstream.
- Patching della VPN **senza** caccia a webshell e credenziali già rubate → errore classico: l’accesso può restare anche dopo il patch.

---

## B. Checklist operativa (con esempi di “cosa cercare”)

### Pre-posizionamento e persistenza

| Controllo | Esempio pratico di ricerca |
|-----------|----------------------------|
| Log autenticazione / EDR pre-escalation | Filtrare login riusciti e processi sospetti dal **1 feb al 27 feb 2026** su segmenti difesa, finance, aeroporti, healthcare |
| RMM non autorizzati | Cercare servizi/processi: `AteraAgent`, `ScreenConnect.ClientService`, `Syncro.Service`, `pdq*`, `SimpleHelp*`. Estrarre **tenant ID** e confronti con inventario ufficiale |
| Implant noti | Hash/famiglie Phoenix, MuddyViper, Tornado, webshell TwoFace-like, beacon su porte documentate (es. 8043, 8848 in advisory storiche MuddyWater) |

### Canali e infrastruttura

| Controllo | Esempio pratico di ricerca |
|-----------|----------------------------|
| Egress satellitare | Alert su traffico da host **non** in lista “mobile/field” verso ASN SpaceX; correlare con orari di blackout Iran (gen e fine feb 2026) |
| Shared hosting Namecheap | Connessioni verso `68.65.122.203` o altri IP AS22612 noti + risoluzione di `*.privatedns.org` del set Tornado |
| Telegram anomalo | Host server o workstation che contattano `api.telegram.org` senza business case (bot token in clear, chat ID ricorrenti) |

### OT / ICS

| Controllo | Esempio pratico di ricerca |
|-----------|----------------------------|
| Esposizione PLC | Scan esterno/interno per porte 44818 (EtherNet/IP), 102 (S7), 502 (Modbus), 20256 (Unitronics); verificare default password |
| Modifiche sospette | Cambio testo HMI, disable di allarmi/shutdown, accessi engineering da IP VPS o da range già in AA26-097A |
| Timeline | Allineare eventi OT a **marzo–aprile 2026** e all’advisory AA26-097A (7 apr 2026) |

### Attribuzione e bias

| Controllo | Esempio pratico |
|-----------|-----------------|
| Non single-IOC | IP Namecheap da solo → insufficiente; serve dominio + comportamento + timing |
| Incertezza documentata | In report: “Tooling coerente con MuddyWater; possibile overlap MaaS; confidenza media sull’attribuzione nazionale” |
| Claim vs telemetria | Allegare screenshot di claim Telegram **separati** dalla sezione “evidenza tecnica” |

---

## C. Mini-playbook per segnale dominante

**Caso: troviate un agent Atera non in inventario**
1. Isolare host e catturare tenant ID + configurazione.
2. Verificare mailbox e log email (spesso foothold da phishing/mailbox già compromessa).
3. Cercare altri RMM e lateral movement nella stessa subnet.
4. Confrontare timing con finestre MuddyWater 2025–2026.
5. Non escludere overlap con altre attività sullo stesso ambiente (OilRig/Lyceum).

**Caso: ransomware dopo exploit su VPN**
1. Identificare CVE e data di exploit vs data di encryption.
2. Cercare webshell e tunnel residui sull’edge device **anche se già patchato**.
3. Verificare se l’affiliate è tra quelli collaborativi con Fox Kitten (ALPHV, NoEscape, RansomHouse).
4. Trattare l’incidente come potenzialmente ibrido (upstream state-linked) fino a prova contraria.

**Caso: allarme su PLC / HMI alterato**
1. Verificare se il controller era esposto e con credenziali deboli/default.
2. Conservare immagini HMI e log di accesso engineering.
3. Confrontare IP sorgente con range pubblici AA26-097A / AA23-335A.
4. Separare effetto tecnico verificabile da eventuali claim Telegram.

**Caso: traffico verso shared hosting USA + Telegram**
1. Risolvere domini e verificare pattern `privatedns.org` / DGA.
2. Cercare exfiltration con naming tipo `L<timestamp>...` se si dispone di campioni o log applicativi.
3. Valutare coerenza con Prince of Persia 2026 (volume vittime basso, targeting mirato).

---

## D. Domande di secondo livello (team di analisi)

1. Stiamo dando più peso a un claim Telegram che a tre settimane di beacon silenzioso pre-28 febbraio?
2. Stiamo usando la stessa etichetta “Iranian APT” per un RMM stealth e per un defacement di PLC?
3. I nostri alert GeoIP ignorano ancora gli ASN satellitari e il shared hosting multi-tenant?
4. Abbiamo scritto nero su bianco le incertezze di attribuzione (tooling condiviso, possibile MaaS, precedente di hijacking infrastrutturale)?
5. La nostra baseline “host che possono usare Starlink / RMM” è aggiornata, o tutto l’egress satellitare finisce nel rumore?

---

## E. Come usare questo documento

| Contesto | Sezioni |
|----------|---------|
| IR in corso (prime ore) | A + B + mini-playbook C più vicino ai segnali |
| Threat hunting settimanale | B (tabelle) + controlli RMM/Starlink/Namecheap |
| Briefing dirigenziale / LE | A (tempistica e tipo attore) + D (bias) |
| Report di attribuzione | Sempre D + colonna “incertezza documentata” |

---

*Esempi ancorati a casi e advisory pubblici (AA24-241A, AA26-097A, Semperis Prince of Persia, reporting MuddyWater/Starlink). Non sostituisce procedure interne di SOC o autorità.*
