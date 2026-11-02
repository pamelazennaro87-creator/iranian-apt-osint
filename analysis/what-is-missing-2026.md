# Cosa manca nelle narrazioni pubbliche (2026)

Questo documento integra i cluster già trattati nel repository e li legge insieme alla timeline geopolitica **senza inventare collegamenti operativi**.  
L’obiettivo è evidenziare prospettive poco enfatizzate e lacune analitiche ricorrenti.

---

## 1. Non esiste “la risposta cyber iraniana”

La maggior parte dei briefing parla di “Iranian APT activity” come se fosse un blocco unico. I dati pubblici dicono altro.

| Cluster / famiglia | Comportamento osservato sotto lo stress del 2026 | Sponsor tipicamente attribuito |
|--------------------|--------------------------------------------------|--------------------------------|
| Prince of Persia | Downtime lungo (~3 mesi), poi rebuild con forte camuffamento (shared hosting USA) | Stato iraniano (profilo storico) |
| MuddyWater | Pre-posizionamento, resilienza (Starlink, RMM), ripresa operativa | MOIS |
| APT34 / OilRig | Presenza su reti USA di interesse prima degli strike; ripresa post-quiete | MOIS (con sfumature) |
| CyberAv3ngers / OT IRGC | Attività su PLC documentata in piena fase di ostilità (AA26-097A) | IRGC-CEC |
| Fox Kitten | Ruolo di access broker + collaborazione ransomware (documentato 2024, contesto ancora rilevante) | Governo iraniano (con componente non pienamente sanzionata) |
| Handala / personas | Uso di Starlink durante blackout; claim e operazioni disruptive | MOIS-linked (persona) |

**Cosa manca:** un modello che tratti esplicitamente l’**eterogeneità di resilienza e di missione** invece di aggregare tutto sotto “Iranian cyber retaliation”.  
Sotto lo stesso shock geopolitico alcuni cluster si spengono, altri restano operativi, altri prioritizzano effetti OT. Questo è un segnale strutturale, non rumore.

---

## 2. Il pre-posizionamento pesa più dei claim post-strike

Fonti multiple indicano implant e infrastruttura MuddyWater/APT34 su reti USA (difesa, banking, aeroporti, healthcare) **nelle settimane precedenti** il 28 febbraio 2026.  
Esiste anche un burst di nuova infrastruttura MuddyWater nei mesi precedenti (set 2025 e gen 2026).

**Cosa viene detto poco:**  
La qualità dell’accesso ottenuto *prima* del trigger cinetico è spesso più informativa del volume di claim e defacement *dopo*.  
I claim hacktivist e le operazioni rumorose post-28 febbraio catturano attenzione; il lavoro silenzioso di pre-posizionamento definisce le opzioni reali.

---

## 3. Blackout ≠ incapacità (e Starlink non è un dettaglio tecnico)

I blackout internet in Iran (gennaio e fine febbraio) vengono spesso letti come “capacità cyber degradate”.  
I dati pubblici mostrano invece:

- uso di Starlink per C2 da parte di cluster MOIS-linked proprio in quei periodi;
- implant già presenti all’estero che non dipendono dalla connettività domestica;
- operatori e infrastruttura fuori dall’Iran.

**Cosa manca:** trattare la connettività satellitare e i canali esteri come **variabile strategica di resilienza**, non come curiosità tecnica.  
Chi dipendeva da infrastruttura domestica o da C2 facilmente spegnibili ha sofferto di più (Prince of Persia). Chi aveva già diversificato ha continuato.

---

## 4. Due sponsor, abitudini diverse — ancora sottoutilizzato in fase di conflitto

Le guide pubbliche distinguono da tempo IRGC e MOIS:

- **IRGC-linked:** spesso più orientati a personas, effetti visibili, OT/defacement, influenza.
- **MOIS-linked:** intrusioni lunghe, possibile hand-off verso wiper/leak, uso di tooling e RMM, a volte rapporti con ecosistemi criminali (MaaS, access brokerage).

Sotto conflitto questa distinzione diventa operativa:
- attività OT e PLC in piena ostilità → coerente con priorità IRGC-CEC;
- pre-posizionamento e resilienza C2 → più visibile nei cluster MOIS;
- Prince of Persia (profilo più “classico” di spionaggio/dissidenti) mostra fragilità infrastrutturale maggiore.

**Cosa manca:** usare sistematicamente questa distinzione quando si interpreta *chi* sta facendo *cosa* in una finestra di crisi, invece di attribuire tutto a “Iran”.

---

## 5. Il precedente Turla–OilRig (2018) come monito metodologico

È documentato che attori russi (Turla) abbiano preso controllo di infrastruttura C2 di OilRig e l’abbiano usata contro le stesse vittime, facendo apparire fingerprint iraniani mentre la collection andava altrove.

**Cosa questo implica per il 2026 (senza inventare nuovi hijacking):**  
In un ambiente ad alta tensione, con molti cluster attivi e infrastruttura in migrazione (shared hosting, Cloudflare, Starlink), il rischio di **sovrapposizione, riuso o interpretazione errata dei fingerprint** aumenta.  
L’attribuzione basata solo su tooling o su un singolo C2 diventa più fragile proprio quando il bisogno di certezze è più alto.

---

## 6. Dentro l’Iran: visibilità asimmetrica

Il reporting pubblico è sbilanciato verso operazioni *in uscita*.  
Dentro l’Iran: concentrazione di servizi, controlli di connettività, sorveglianza domestica e scarsa disclosure riducono la visibilità di incidenti, effetti collaterali e possibili compromise di infrastruttura usata dagli stessi operatori.

**Cosa manca:**  
Trattare esplicitamente il bias di osservazione. Ciò che non vediamo all’interno non può essere usato per gonfiare o sgonfiare stime di capacità, ma deve restare come incertezza strutturale nelle valutazioni.

---

## 7. Cosa nessuno sta mettendo al centro (sintesi)

1. **Eterogeneità sotto stress** — non una campagna unica, ma risposte diverse per cluster e sponsor.  
2. **Pre-posizionamento come segnale primario** — più dei claim post-evento.  
3. **Resilienza di canale (Starlink, RMM, implant esteri)** come discriminante tra chi regge e chi si spegne.  
4. **Camuffamento infrastrutturale (Namecheap shared hosting)** come possibile effetto collaterale della pressione geopolitica e della ricerca pubblica, non solo come tattica isolata.  
5. **Fragilità dell’attribuzione in fase di crisi** — precedente Turla/OilRig come monito, non come accusa corrente.  
6. **Asimmetria di visibilità** — fuori vs dentro l’Iran.

Nessuno di questi punti richiede di inventare un coordinamento segreto tra tutti i cluster.  
Richiede solo di leggere insieme i dati già pubblici invece di trattarli come silos o come un’unica “macchina iraniana”.

---

## Collegamenti nel repository

- `analysis/geopolitical-cyber-correlation-2026.md`
- `analysis/prince-of-persia-detailed.md`
- `analysis/starlink-iranian-actors.md` + `starlink-hunting-notes.md`
- `groups/muddywater.md` / `fox-kitten.md` / `cyberav3ngers.md`
- `analysis/divergent-connections.md`
- `analysis/aggressive-research-agenda.md`

---

*Documento di prospettiva. Non attribuisce operazioni non documentate. Serve a orientare domande migliori.*
