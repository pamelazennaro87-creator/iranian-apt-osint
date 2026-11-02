# Agenda di ricerca aggressiva – Fronti prioritari

Documento operativo per spingere su tutte le direzioni ad alto potenziale investigativo ancora poco saturato.  
Ogni fronte include: stato attuale delle evidenze, prossima mossa concreta, e valore atteso per forze dell’ordine / difensori.

---

## Fronte 1 — Starlink come C2 e come arma

**Stato**  
- Uso C2 confermato per MuddyWater (fine 2025–inizio 2026) e Handala (durante blackout).  
- Uso del brand come lure (DCHSpy).  
- Regime iraniano in fase di contrasto attivo (jamming claims, GPS spoofing, sequestri).

**Prossime mosse aggressive**  
1. Mappare gateway/IP di uscita SpaceX noti nei periodi di attività MuddyWater e correlarli con beacon noti.  
2. Verificare se campioni MuddyWater di quel periodo contengono logiche di fallback satellitare o user-agent/timeout particolari.  
3. Incrociare timeline di blackout internet in Iran con picchi di attività C2 satellitare.  
4. Cercare overlap tra terminali sequestrati in operazioni IRGC e infrastruttura usata da cluster MOIS.

**Valore**  
Alto. Cambia il modello di detection e apre possibili pivot su supply chain dei terminali.

---

## Fronte 2 — Shared hosting / Namecheap come zona di camuffamento

**Stato**  
- Prince of Persia 2026: primo C2 USA su shared hosting Namecheap in 10 anni, mescolato a domini legittimi e altri threat actor.  
- Pattern ricorrente di uso Namecheap da parte di più cluster iraniani.

**Prossime mosse aggressive**  
1. Costruire lista di IP Namecheap / shared hosting già legati a cluster iraniani e verificare co-hosting di altri attori (criminali o statali).  
2. Analizzare certificati, pannelli (cPanel vs altri), e pattern di registrazione dominio sullo stesso range.  
3. Verificare se altri gruppi iraniani hanno migrato verso shared hosting USA o europei nello stesso arco temporale (post-feb 2026).  
4. Trattare il “rumore” del shared hosting non come ostacolo ma come possibile grafo di relazioni.

**Valore**  
Molto alto per infrastructure hunting. Può rivelare connessioni trasversali non visibili a livello di malware family.

---

## Fronte 3 — MuddyWater × ecosistema MaaS russofono

**Stato**  
- Reporting 2026 indica MuddyWater come cliente di piattaforma MaaS russofona (certificati di code-signing e infrastruttura adiacente).

**Prossime mosse aggressive**  
1. Estrarre tutti i certificati di firma e builder associati a campioni MuddyWater 2025–2026 e cercarli in cluster criminali non attribuiti.  
2. Verificare victim overlap o infrastruttura C2 condivisa/adiacente tra operazioni MuddyWater e campagne criminali dello stesso MaaS.  
3. Valutare se il rapporto è solo “acquisto di tooling” o se esiste accesso a vittime o dati in entrambe le direzioni.

**Valore**  
Alto. Rompe l’assunzione che tooling = attribuzione nazionale e apre linee di indagine ibride stato-criminale.

---

## Fronte 4 — Fox Kitten feedback loop (accesso → ransomware → possibile ritorno)

**Stato**  
- Collaborazione operativa documentata con ALPHV, NoEscape, RansomHouse (non solo vendita passiva di accessi).  
- FBI valuta l’attività ransomware come probabilmente non pienamente sanzionata, ma il confine è poroso.

**Prossime mosse aggressive**  
1. Nei casi ransomware degli affiliate nominati, cercare sistematicamente indicatori di edge exploitation Fox Kitten (CVEs edge, webshell in path non standard, tunneling).  
2. Mappare se gli stessi accessi usati per ransomware appaiono poi in attività di raccolta intelligence.  
3. Trattare ogni incidente ransomware “russo” con questi affiliate come potenziale caso ibrido fino a prova contraria.

**Valore**  
Critico per le forze dell’ordine. Cambia la qualificazione giuridica e investigativa di interi incidenti.

---

## Fronte 5 — Overlap operativi e access sharing (MuddyWater ↔ OilRig/Lyceum e oltre)

**Stato**  
- Documentato overlap di vittima e temporale (utilities israeliane, 2025).  
- Ipotesi di MuddyWater come possible initial access broker anche verso altri cluster iraniani.

**Prossime mosse aggressive**  
1. Costruire timeline unificata di compromissioni note e cercare vittime condivise tra cluster MOIS e IRGC.  
2. Verificare se tooling o infrastruttura di un cluster appare in ambienti già compromessi dall’altro.  
3. Valutare se esiste un livello di coordinamento o di mercato interno degli accessi.

**Valore**  
Alto per capire la struttura reale dell’ecosistema (gerarchico, a silos, o a mercato interno).

---

## Fronte 6 — Pattern di errore OPSEC come firma

**Stato**  
- Già documentati errori ricorrenti (default credentials, RMM, engineering tool da VPS, claim esagerati, AI residual).

**Prossime mosse aggressive**  
1. Trasformare ogni classe di errore in regola di hunting testabile.  
2. Cercare nuovi errori emergenti (es. uso di AI, certificati riutilizzati, timezone leak, language artifact).  
3. Usare gli errori non solo per detection ma per collocare gli operatori (fuso orario, strumenti preferiti, livello di professionalità).

**Valore**  
Durevole. Gli IOC muoiono; gli errori comportamentali persistono.

---

## Priorità di esecuzione consigliata

1. **Immediata:** Fronte 2 (Namecheap/shared hosting) + Fronte 4 (Fox Kitten in casi ransomware).  
2. **Breve termine:** Fronte 1 (Starlink correlation) + Fronte 3 (MaaS certificates).  
3. **Continua:** Fronte 5 e 6 come lavoro di fondo su ogni nuovo report.

---

*Questo agenda è viva. Ogni nuova evidenza pubblica deve essere usata per chiudere, rafforzare o eliminare le ipotesi.*
