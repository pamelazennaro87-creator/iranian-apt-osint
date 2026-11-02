# Connessioni divergenti e angoli poco esplorati

Questo documento raccoglie ipotesi e osservazioni che escono dagli schemi di attribuzione classici.  
Ogni punto è esplicitamente etichettato per confidenza e utilità investigativa. L’obiettivo è generare domande e pivot che i report vendor standard raramente pongono.

---

## 1. L’anomalia Prince of Persia 2026: C2 su shared hosting USA

**Osservazione (alta confidenza – Semperis)**  
Per la prima volta dal 2016, Prince of Persia ha posizionato un C2 Tornado (68.65.122.203) su shared hosting Namecheap negli Stati Uniti, mescolato a migliaia di domini legittimi e ad altri attori malevoli (inclusi typosquatting Roblox).

**Angolo divergente**  
Non è solo “hanno cambiato provider”. È una scelta di **camuffamento ambientale**:
- Abbandono del modello VPS dedicato.
- Scelta deliberata di un ambiente multi-tenant denso di rumore.
- Timing correlato a un periodo di tensione geopolitica (dopo febbraio 2026).

**Domande investigative poco poste**  
- Il passaggio a shared hosting USA è stato forzato da pressione su provider europei, da necessità di ridondanza, o da test di deception?
- Esistono altri cluster iraniani (o non iraniani) che nello stesso periodo hanno fatto la stessa migrazione su Namecheap shared?
- Il fatto che lo stesso IP/hosting ospiti anche infrastruttura di altri threat actor crea opportunità di pivot laterale tra campagne apparentemente non correlate?

**Utilità**  
Alta per chi fa infrastructure hunting: il segnale non è più “IP in Iran/Europa”, ma “comportamento di blending su shared hosting USA + cambio di pannello di gestione (Cyber Panel → cPanel)”.

---

## 2. MuddyWater come cliente di MaaS russofono

**Osservazione (media-alta confidenza – reporting 2026)**  
MuddyWater è stato identificato come cliente di una piattaforma Malware-as-a-Service gestita da attori russofoni. Elementi di sovrapposizione includono certificati di code-signing e infrastruttura condivisa/adiacente.

**Angolo divergente**  
Un attore statale (MOIS) che **noleggia** tooling da un ecosistema criminale straniero inverte il modello classico “stato sviluppa, criminali copiano”. Qui lo stato compra capacità tattica sul mercato.

**Implicazioni poco discusse**  
- Le famiglie malware usate da MuddyWater in certi periodi possono condividere DNA, certificati o infrastruttura con campagne puramente criminali non iraniane.
- L’attribuzione basata solo su tooling diventa più fragile.
- Esiste un potenziale flusso inverso: tecniche o accessi sviluppati in contesti criminali che finiscono in operazioni di intelligence.

**Domanda investigativa**  
Quando si trova un campione o un C2 legato a MuddyWater, conviene sistematicamente verificare se lo stesso certificato, lo stesso builder o la stessa infrastruttura appaiono in cluster criminali non attribuiti all’Iran.

---

## 3. Fox Kitten: il feedback loop accesso → ransomware → possibile ritorno di intelligence

**Osservazione (alta confidenza – AA24-241A)**  
Fox Kitten non si limita a vendere accessi: collabora operativamente con affiliate ransomware (ALPHV, NoEscape, RansomHouse) e prende una quota.

**Angolo divergente**  
Quasi nessuno modello pubblico esplora il **ciclo di ritorno**:
1. Accesso ottenuto per spionaggio o brokerage.
2. Accesso monetizzato tramite ransomware.
3. I proventi (o le informazioni raccolte durante la fase ransomware) possono finanziare o informare successive operazioni di intelligence?

Anche se il FBI valuta l’attività ransomware come probabilmente non pienamente sanzionata dallo stato, il confine operativo è poroso. Un incidente che inizia come “ransomware russo” può avere un upstream iraniano e, in teoria, un downstream di dati utili allo stato.

**Utilità per le forze dell’ordine**  
Nei casi ransomware che coinvolgono gli affiliate nominati, la ricerca di indicatori Fox Kitten (edge exploitation, webshell in path non standard, tunneling) non è solo “nice to have”: può cambiare la natura dell’indagine da criminale a ibrida stato-criminale.

---

## 4. Starlink come doppio strumento

**Osservazioni pubbliche**  
- MuddyWater e altri attori iraniani hanno sperimentato C2 via Starlink (2025–2026).
- Allo stesso tempo, malware legati a MuddyWater hanno usato il nome “Starlink” come lure contro utenti iraniani assetati di internet non filtrato.
- Funzionari iraniani descrivono pubblicamente Starlink come “strumento di guerra” e affermano di avere capacità di interferenza.

**Angolo divergente**  
Lo stesso canale satellitare è contemporaneamente:
- Mezzo di C2 per operatori iraniani all’estero o in condizioni di blackout.
- Vettore di social engineering contro la popolazione iraniana.
- Bersaglio retorico e tecnico del regime.

Questo crea un ecosistema in cui il traffico Starlink può essere sia offensivo che difensivo a seconda del punto di osservazione, complicando attribution e detection basate sulla sola presenza del servizio.

---

## 5. Ipotesi di lavoro prioritaria (da testare)

| Ipotesi | Confidenza attuale | Come falsificarla / rafforzala |
|---------|--------------------|--------------------------------|
| Esiste un sottoinsieme di infrastruttura Namecheap/shared hosting usata in modo ricorrente da più cluster iraniani + attori criminali | Bassa-media | Mapping sistematico di certificati, pannelli, e co-hosting su IP Namecheap noti |
| MuddyWater e alcuni cluster criminali russofoni condividono non solo tooling ma finestre operative o accessi | Media | Correlazione temporale + certificati + victim overlap |
| Il passaggio di Prince of Persia a US shared hosting è un segnale di pressione infrastrutturale più ampio sull’ecosistema iraniano | Bassa | Verificare se altri gruppi hanno fatto migrazioni analoghe nello stesso periodo |
| I proventi o i dati delle operazioni ransomware abilitate da Fox Kitten alimentano in parte attività di intelligence | Speculativa | Richiede dati non pubblici (flussi finanziari, tasking) |

---

## Nota metodologica

Queste connessioni sono **volutamente speculative nei punti deboli** e ancorate a fonti pubbliche nei punti forti.  
Servono a generare linee di ricerca, non a costituire attribuzione.  
Qualsiasi uso operativo deve partire dalla verifica primaria delle fonti e dalla raccolta di nuove evidenze.

*Ultimo aggiornamento: 2026-11-02*
