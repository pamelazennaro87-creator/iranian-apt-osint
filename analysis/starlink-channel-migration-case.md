# Scheda caso: Starlink come migrazione di canale

Progetto **Infrastructure under pressure** · metodo in `infrastructure-migration-method.md`.

Qui la “migrazione” non è un cambio di VPS, ma l’**aggiunta o lo spostamento del path di connettività operativa** verso uplink satellitare (SpaceX/Starlink) quando la rete terrestre iraniana viene spenta o degradata.

---

## 1. Ancoraggio pre-evento

| Dimensione | Stato tipico pre-blackout (cluster MOIS-linked) |
|------------|--------------------------------------------------|
| Canale C2 dominante in report | VPS / hosting estero, HTTP(S), a volte RMM, Telegram come supporto |
| Dipendenza da uplink domestico Iran | Variabile: operatori e C2 spesso già fuori Iran; parte del controllo e della presenza online passa comunque da connettività locale |
| GeoIP / ASN attesi in telemetria vittima | ASN di VPS europei/mediorientali, cloud commerciali, non satellitari |

Baseline: molti cluster iraniani *già* usano infrastruttura estera. Il punto debole in blackout non è sempre il C2 in sé, ma la capacità degli operatori di restare online e di far uscire traffico da dentro l’Iran.

---

## 2. Trigger documentati (date)

| Data / finestra | Evento |
|-----------------|--------|
| ~8 gennaio 2026 | Blackout / collasso traffico internet Iran (report NetBlocks, Cloudflare: calo estremo) |
| Metà gennaio 2026 in poi | Check Point: Handala usa Starlink per restare online (Forbes, 2–3 mar 2026) |
| Fino ad almeno 28 febbraio 2026 | Stesso reporting: uso Starlink continua almeno fino al giorno degli strike |
| Gennaio 2026 | LRQA assessment: Void Manticore adatta operazioni usando indirizzi IP Starlink durante il blackout |
| Parallelamente | Regime: jamming / misure contro terminali Starlink (dichiarazioni successive su disabilitazione “controllata” e packet loss elevato) |

Causalità operativa: **non dimostrata oltre il timing**. Il legame utile è: blackout terrestre → comparsa/conferma di path satellitare in report tecnici.

---

## 3. Rottura e “dopo”

| Dimensione | Prima (tipico) | Dopo (osservato in report) |
|------------|----------------|----------------------------|
| Uplink operatori / presenza online | Rete fissa/mobile Iran o mix | Path Starlink documentato per Handala; IP Starlink citati per Void Manticore |
| Tipo di migrazione | — | **Di canale** (+ resilienza): non sostituisce necessariamente il C2 VPS, aggiunge path indipendente dal backbone iraniano |
| Visibilità GeoIP | ASN terrestri | ASN SpaceX / range Starlink in telemetria o in analisi di chi osserva gli operatori |
| Contesto regime | Starlink illegale / osteggiato | Stesso strumento usato da attori linkati allo Stato per restare operativi — tensione strutturale, non aneddoto |

**Nota:** Handala in questa finestra è anche molto presente sul piano narrativo (minacce, claim). Per questa scheda conta solo il pezzo **infrastrutturale** (Starlink come path), non i claim su operazioni esterne.

---

## 4. Classificazione (metodo)

| Tipo | Applicabile? |
|------|----------------|
| Geografica | Parziale (uscita verso costellazione / ground infrastructure SpaceX, non “paese C2 classico”) |
| Densità (shared vs dedicato) | No (non è il punto) |
| Stack / pannello | No |
| **Canale** | **Sì — primario** |
| **Resilienza** | **Sì — primario** |
| Reattiva alla ricerca vendor | Non il driver principale; driver visibile = blackout / restrizione terrestre |

---

## 5. Segnali cacciabili (output operativo)

1. **Host aziendali fissi** (non laptop di campo autorizzati) con egress ricorrente verso **ASN SpaceX / range Starlink**.  
2. Correlazione temporale: stesso host o stesso cluster di beacon **attivi durante finestre di blackout Iran** note.  
3. Combinazione: traffico Starlink-side *e* tooling/RMM/Telegram già associati a cluster MOIS-linked in report pubblici.  
4. Non alertare “ogni IP Starlink”: prioritizzare **baseline assente** (quell’host non doveva usare uplink satellitare).  
5. Lato analisi operatori: account / infrastruttura di claim che restano online mentre il traffico nazionale Iran collassa — indizio di path alternativo (da confermare tecnicamente, non solo dal fatto di postare su X/Telegram).

---

## 6. Solido / ipotesi / sconosciuto

**Solido (fonti pubbliche)**  
- Blackout gennaio 2026 con crollo traffico documentato.  
- Check Point (via Forbes): Handala su Starlink almeno da metà gennaio fino a ≥ 28 feb 2026.  
- LRQA: Void Manticore usa IP Starlink per sostenere operazioni nel blackout di gennaio.  
- Starlink in Iran è osteggiato/illegale; misure di jamming e claim di disabilitazione da parte del regime sono pubblici (qualità tecnica variabile).

**Ipotesi**  
- Uso Starlink come path standard di più cluster oltre Handala / Void Manticore.  
- Stesso path usato in modo sistematico anche fuori dalle finestre di blackout.  
- Coordinamento centralizzato “usate Starlink” vs adozione opportunistica per cluster.

**Sconosciuto da sole fonti aperte**  
- Volumi, durata esatta post-febbraio, lista IP/ASN precisi riusabili come blocklist.  
- Se il path satellitare porta il C2 vittima→attore o soprattutto la connettività operatore→mondo.  
- Dettaglio forense dei terminali / ground station path.

---

## 7. Implicazioni per indagine e difesa

- I playbook basati solo su GeoIP “paese VPS” **perdono** chi esce da ASN satellitari.  
- In finestre di blackout Iran, alzare la priorità di hunting su egress SpaceX da asset che non hanno business case satellitare.  
- Non confondere: “attore iraniano” ≠ “traffico originato da IP iraniani terrestri”.  
- Dual-use: lo stesso canale serve dissidenti e, in report, operatori offensivi — l’analisi deve restare sul comportamento tecnico, non sull’etica del mezzo.

---

## 8. Collegamenti

- Metodo: `analysis/infrastructure-migration-method.md`  
- Progetto: `analysis/infrastructure-under-pressure.md`  
- Note hunting già presenti: `analysis/starlink-hunting-notes.md`, `analysis/starlink-iranian-actors.md`  
- Geopolitica: `analysis/geopolitical-cyber-correlation-2026.md`  

---

*Scheda caso canale. Prossimo passo nel progetto: segnali di migrazione estratti da Prince of Persia (densità/stack/geografia).*  

Fonti ancora: Forbes (Check Point / Handala Starlink), LRQA Iran CTI assessment 2026, NetBlocks/Cloudflare sul blackout, reporting su contromisure regime anti-Starlink.
