# Analisi dettagliata – Prince of Persia 2026

**Fonte primaria di riferimento:** Semperis Research, “Prince of Persia: A Threat Group Hiding in Plain Sight” (22 ottobre 2026) + reporting correlato.  
**Obiettivo:** estrarre il massimo valore investigativo e difensivo dalla migrazione infrastrutturale e dal comportamento operativo osservato.

---

## 1. Chi è e cosa fa

Prince of Persia (anche noto storicamente come Infy) è un attore APT iraniano attivo da circa due decenni.  
Target principali documentati:
- Dissidenti iraniani
- Organizzazioni pubbliche e private in USA, Europa e Medio Oriente
- Attività storiche legate a operazioni di influenza e controllo interno (es. targeting di media e società civile)

Non risulta motivato finanziariamente in modo primario. Il profilo è coerente con obiettivi di intelligence e controllo interno/esterno.

### Ecosistema malware (evoluzione)

| Famiglia | Ruolo | Note |
|----------|-------|------|
| **Infy** | Tool di spionaggio completo (variante M con GUI nascosta) | Famiglia fondativa; takedown Unit 42 2016 |
| **Foudre** | First-stage | Mapping vittime, persistenza, reconnaissance, credential theft di base; decide se la vittima merita second-stage |
| **Tonnerre** | Second-stage | Surveillance profonda (audio, screenshot, documenti), DGA, Telegram come canale di fallback |
| **Tornado** | Evoluzione multi-stage più recente | HTTPS + Telegram API, DGA, exfiltration anche via campi nascosti in transazioni blockchain, validazione RSA delle richieste C2 per resistere a sinkhole |

Tornado rappresenta il salto di resilienza: non solo nasconde il C2, ma rende più difficile a ricercatori e scanner di mappare l’infrastruttura e le vittime.

---

## 2. Timeline operativa 2026 (ricostruita)

| Data | Evento |
|------|--------|
| 4 feb 2026 | Pubblicazione ricerca SafeBreach |
| < 1 settimana | Spegnimento C2 `45.80.148.249` |
| 9 feb 2026 | Nuovo C2 `45.80.148.194` (stesso range); svuotamento della lista GUID vittime (`updatelist.txt`) |
| 25 feb 2026 | Ultima registrazione dominio nota prima del blackout operativo |
| 28 feb 2026 | Inizio conflitto USA/Israele – Iran |
| Mar – Apr 2026 | C2 inattivi ma registrazione certificati SSL continua fino a inizio aprile |
| ~3 mesi | Downtime più lungo nella storia del gruppo (~due decenni) |
| 27 mag 2026 | Ripresa: nuovo C2 `185.244.129.70` + dominio `aa58862c.ddns.net`; exfiltration Tonnerre riparte (>1800 file in una settimana da una vittima) |
| 31 mag 2026 | Dominio Tornado `xleergjemlwm.hbmc.net` |
| Inizio giu 2026 | Dominio DGA `nnahinsmqs.site` (prefisso tipo `<YY><M><WEEK>G3`) |
| ~7 lug 2026 | Costruzione C2 Tornado second-stage su **Namecheap shared hosting USA** (`68.65.122.203`) |
| Ago 2026 | Scoperta del C2 USA; successiva migrazione di parte dell’infrastruttura dietro Cloudflare (`162.159.24.80`) |

**Pattern chiave:** il gruppo reagisce rapidamente alla ricerca pubblica (spegnimento e rebuild), ma mantiene un filo di attività amministrativa (certificati) anche durante i periodi di inattività operativa. Il downtime più lungo coincide con il picco di tensione geopolitica.

---

## 3. La svolta infrastrutturale: perché è rilevante

### Prima
- Preferenza per range IP europei noti (`45.80.148.0/24`, `45.80.149.0/24`, `45.80.151.0/24`)
- VPS dedicati
- Pannello di gestione: **Cyber Panel** (porta 8090 tipica)

### Dopo (metà 2026)
- Passaggio a **shared hosting Namecheap** (IP `68.65.122.203`, AS22612)
- Ambiente multi-tenant con migliaia di domini legittimi e altri threat actor (es. typosquatting Roblox)
- Cambio pannello → **cPanel**
- Successivo utilizzo di Cloudflare per parte del C2 Tornado

**Interpretazione investigativa**

Questo non è un semplice cambio di provider. È una scelta di **camuffamento ambientale**:
- L’IP da solo perde quasi tutto il valore di intelligence (è condiviso).
- La detection basata su “IP sospetto / VPS low-cost” diventa molto più debole.
- Il gruppo accetta di condividere lo stesso spazio fisico/logico con attori criminali di basso livello per guadagnare opacità.

È il comportamento opposto a quello di molti APT che cercano infrastruttura “pulita” e controllata. Qui si cerca deliberatamente il rumore.

---

## 4. Indicatori pubblici utili (riepilogo operativo)

**C2 Namecheap (caso centrale)**  
- IP: `68.65.122.203`  
- Domini: `kxzsfydnivzmv.privatedns.org` e altri `*.privatedns.org` dello stesso set  
- ASN: AS22612 (Namecheap)

**Altri IP del periodo**  
- `162.159.24.80` (Cloudflare, post-esposizione)  
- `185.244.129.70` / `185.244.129.123`  
- Range storico: `45.80.148.0/24` e adiacenti (pre-migrazione)

**Comportamenti collaterali ad alto valore**  
- Uso di Telegram API / bot per exfiltration e C2 di fallback  
- DGA con pattern riconoscibile  
- Validazione RSA delle richieste C2 (anti-sinkhole)  
- Formato file esfiltrati osservato: `L<YY><MM><DD><HH><MM><SS><IP vittima azzerato>`

---

## 5. Implicazioni per indagini e difesa

1. **Hunting infrastrutturale**  
   Cercare non solo gli IP, ma il pattern: shared hosting Namecheap + cPanel + domini privatedns.org / DGA + traffico Telegram anomalo.

2. **Reazione alla ricerca**  
   Il gruppo dimostra monitoring attivo delle pubblicazioni di sicurezza. Dopo ogni report di rilievo ci si aspetta spegnimento rapido e rebuild.

3. **Correlazione geopolitica**  
   I periodi di tensione con USA/Israele producono downtime prolungati. Questo può essere usato come finestra predittiva (riduzione di attività) o come momento di possibile ricostruzione infrastrutturale.

4. **Targeting**  
   Il numero di vittime osservate resta basso → attività mirata più che opportunistica di massa. Le vittime attive continuano a essere esfiltrate nel tempo.

5. **Resilienza**  
   Combinazione di DGA + Telegram + (in Tornado) elementi blockchain + RSA anti-sinkhole indica investimento su persistenza e anti-analisi, non solo su volume.

---

## 6. Domande ancora aperte (per ricerca successiva)

- Altri cluster iraniani hanno replicato il passaggio a shared hosting Namecheap nello stesso periodo?
- Esiste co-hosting rilevante (stessi IP o stessi account) tra Prince of Persia e attori criminali presenti sullo stesso ambiente Namecheap?
- Il cambio di pannello (Cyber Panel → cPanel) è solo tattica o riflette un cambio di operatori/tooling interno?
- I certificati registrati durante il downtime contengono indizi su infrastruttura di backup o su identità di registrazione?

---

## 7. Collegamenti nel repository

- `iocs/prince-of-persia-2026.md` — lista IOC pronta all’uso  
- `analysis/divergent-connections.md` — angolo “camuffamento ambientale”  
- `analysis/aggressive-research-agenda.md` — Fronte 2 (Namecheap/shared hosting)

---

*Analisi basata esclusivamente su fonti pubbliche. Destinata a supporto investigativo e di detection. Aggiornare con nuove evidenze.*
