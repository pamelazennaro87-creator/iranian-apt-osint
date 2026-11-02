# Metodo: come si osserva una migrazione infrastrutturale

Parte del progetto **Infrastructure under pressure**.  
Obiettivo: riconoscere e documentare uno spostamento di C2/hosting da fonti aperte, senza inventare nessi e senza trattare un IP condiviso come prova attributiva.

---

## 1. Cosa intendiamo per “migrazione”

Non è solo “un IP nuovo”. È un **cambiamento di classe** di infrastruttura, ad esempio:

| Da | A | Esempio pubblico |
|----|---|------------------|
| VPS dedicato / range noti | Shared hosting multi-tenant | Prince of Persia → Namecheap USA |
| Hosting europeo ricorrente | Hosting USA / altro RIR | Stesso caso |
| Pannello X (es. Cyber Panel) | Pannello Y (es. cPanel) | PoP 2026 |
| IP “nudo” | Dietro CDN (Cloudflare) | PoP post-scoperta |
| Solo HTTP(S) classico | + Telegram / RMM / satellitare | MuddyWater, Tornado, Handala |
| Domini stabili | DGA + domini usa-e-getta | Tornado / Tonnerre |

Una migrazione può essere **parziale** (solo second-stage, solo un malware family) o **totale**.

---

## 2. Sequenza operativa (passi)

### Passo 1 — Ancoraggio pre-evento
Fissa lo stato “prima” con fonti pubbliche:
- range IP / ASN ricorrenti
- registrar e pattern di naming
- pannello di gestione se mai esposto in report
- canali C2 noti (HTTP, Telegram, altro)

*Esempio PoP:* range `45.80.148/149/151`, Cyber Panel :8090, hosting europeo.

### Passo 2 — Trigger da documentare
Segna cosa può aver spinto il cambio (anche se la causalità resta incerte):
- pubblicazione di ricerca tecnica (SafeBreach, Semperis, Unit 42…)
- advisory governativa
- blackout / conflitto / takedown
- semplice rotazione periodica

Registra **date**, non ipotesi sul decision-maker.

### Passo 3 — Rottura di continuità
Cerca segnali che lo stato “prima” non vale più:
- C2 storici spenti o svuotati (es. liste vittime vuote)
- stop di registrazioni domini su pattern vecchio
- certificati che continuano (o smettono) in modo anomalo durante il downtime
- silenzio operativo prolungato rispetto alla baseline del gruppo

### Passo 4 — Comparsa del “dopo”
Documenta la nuova footprint:
- nuovi IP / ASN / country / tipo di hosting (VPS vs shared)
- nuovi domini (incluso DGA se descritto in report)
- cambio di pannello, di porta management, di stack
- comparsa di CDN, di canali paralleli (Telegram, Starlink)

### Passo 5 — Classificare il tipo di migrazione
Assegna una o più etichette (possono coesistere):

| Tipo | Domanda chiave |
|------|----------------|
| **Geografica** | È cambiato paese / RIR / provider “di bandiera”? |
| **Di densità** | Da dedicato/pulito a shared/rumoroso (o viceversa)? |
| **Di stack** | Pannello, OS management, porte, CDN? |
| **Di canale** | Nuovo protocollo o path (Telegram, RMM, satellite)? |
| **Di resilienza** | Aggiunge fallback o anti-sinkhole (DGA, RSA, blockchain fields)? |
| **Reattiva alla ricerca** | Il timing segue di giorni/settimane un report pubblico? |

### Passo 6 — Segnali cacciabili (output utile)
Dalla migrazione tira fuori **comportamenti**, non solo IOC:
- “C2 su shared Namecheap + cPanel + `*.privatedns.org`”
- “Egress host fisso → ASN SpaceX in finestra di blackout”
- “Stesso malware family, cambio pannello management”

Questi restano utili anche quando i singoli IP muoiono.

### Passo 7 — Limiti obbligatori in ogni scheda
Chiudi sempre con tre blocchi:
1. **Solido** — cosa è in report primari / multi-fonte  
2. **Ipotesi** — cosa è plausibile ma non dimostrato  
3. **Sconosciuto** — cosa non si può dire da fonti aperte  

---

## 3. Schema “prima → dopo” (template)

Usare una tabella per ogni caso:

| Dimensione | Prima | Dopo | Fonte | Data approx |
|------------|-------|------|-------|-------------|
| ASN / provider | | | | |
| Paese / RIR | | | | |
| Tipo hosting | VPS / shared / CDN | | | |
| Pannello / porte mgmt | | | | |
| Pattern domini | | | | |
| Canali C2 | | | | |
| Note operative | | | | |

---

## 4. Applicazione al caso Prince of Persia (sintesi)

| Dimensione | Prima | Dopo |
|------------|-------|------|
| Provider / range | Range EU noti `45.80.x` | Namecheap shared `68.65.122.203` (AS22612), poi Cloudflare |
| Tipo hosting | VPS / dedicato ricorrente | Shared multi-tenant (rumore alto) |
| Pannello | Cyber Panel :8090 | cPanel |
| Reazione a ricerca | Spegnimento rapido post-SafeBreach (feb 2026) | Rebuild dopo downtime ~3 mesi |
| Contesto | Pre-conflitto | Durante/dopo inizio ostilità USA–Iran; C2 USA inedito da ~10 anni |

**Tipo di migrazione:** geografica + densità (shared) + stack (pannello) + parziale uso CDN; timing compatibile con reazione a ricerca *e* con stress geopolitico (causalità non dimostrata oltre il timing).

Dettaglio: `analysis/prince-of-persia-detailed.md`.

---

## 5. Errori da evitare

- Trattare un IP shared come “infrastruttura dell’attore” in senso esclusivo  
- Confondere rotazione normale di domini con cambio di *classe* infrastrutturale  
- Attribuire la migrazione a un ordine politico solo perché le date coincidono  
- Ignorare i canali paralleli (Telegram/RMM/satellite): a volte la “migrazione” è l’aggiunta di un path, non la sostituzione dell’IP  
- Pubblicare liste di IP senza finestra temporale e senza tipo di hosting  

---

## 6. Output atteso di ogni nuova scheda caso

1. Tabella prima/dopo  
2. Tipo(i) di migrazione  
3. Trigger documentati (date)  
4. 3–7 segnali cacciabili  
5. Solido / ipotesi / sconosciuto  

---

*Metodo riproducibile. Prossimo utilizzo naturale: scheda Starlink (canale) e checklist segnali di migrazione estratti da PoP.*
