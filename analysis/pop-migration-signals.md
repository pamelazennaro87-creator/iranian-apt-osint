# Segnali di migrazione — estratti da Prince of Persia 2026

Progetto **Infrastructure under pressure**.  
Fonte primaria del caso: Semperis (ott 2026) + scheda `prince-of-persia-detailed.md`.  
Metodo: `infrastructure-migration-method.md`.

Obiettivo: trasformare il caso PoP in **segnali riusabili** su altri cluster, non in una lista di IP da bloccare e dimenticare.

---

## 1. Tabella prima → dopo (richiamo)

| Dimensione | Prima | Dopo |
|------------|-------|------|
| Range / provider | `45.80.148/149/151` (EU, pattern ricorrente) | Namecheap shared `68.65.122.203` (AS22612), poi Cloudflare `162.159.24.80` |
| Tipo hosting | VPS / footprint “pulita” ricorrente | Shared multi-tenant (migliaia di domini, rumore alto) |
| Pannello | Cyber Panel :8090 | cPanel |
| Geografia percepita | Europa | USA (prima volta in ~10 anni per questo gruppo, per il C2 second-stage Tornado) |
| Timing | Pre-report SafeBreach / pre-conflitto | Spegnimento rapido post-ricerca (feb); downtime ~3 mesi; ripresa mag; shared USA ~lug |

---

## 2. Segnali cacciabili (riusabili)

### A. Cambio di densità (il più distintivo)

| Segnale | Perché conta | Come usarlo |
|---------|--------------|-------------|
| C2 o pannello che compare su **shared hosting** dopo anni di VPS dedicati | Aumenta opacità; l’IP da solo perde valore attributivo | In hunting: non scartare shared solo perché “rumoroso”; correlare dominio + comportamento + timing |
| Stesso malware family, **stesso stile di management**, provider diverso | Continuità operativa sotto nuova footprint | Cercare invarianti (path PHP noti, formato exfil, Telegram bot pattern) anche quando cambia ASN |

### B. Cambio di stack di management

| Segnale | Perché conta | Come usarlo |
|---------|--------------|-------------|
| Passaggio **Cyber Panel → cPanel** (o altro pannello) | Indizio di rebuild, non solo rotazione IP | Se in passato un cluster era legato a una porta/pannello, un silenzio + ricomparsa su altro stack merita scheda migrazione |
| Porta management esposta storicamente (es. 8090) che sparisce dalla footprint pubblica | Rottura di continuità | Documentare la scomparsa come passo 3 del metodo (rottura), non solo i nuovi IOC |

### C. Reazione alla ricerca pubblica

| Segnale | Perché conta | Come usarlo |
|---------|--------------|-------------|
| Spegnimento C2 **entro giorni** da report tecnico dettagliato | Monitoring attivo della letteratura CTI da parte dell’attore | Dopo report major su un cluster, aspettarsi finestra di rebuild; alzare hunting su *nuove* footprint, non solo IOC vecchi |
| Svuotamento liste vittime / file di stato sul C2 prima dello shutdown | Tentativo di ridurre danno da sinkhole/analisi | Se si ha accesso forense a C2 (LE), conservare timeline di cancellazione |

### D. Geografia e CDN

| Segnale | Perché conta | Come usarlo |
|---------|--------------|-------------|
| C2 su **territorio USA** da attore storicamente EU-hosted | Rottura di abitudine geografica | Non usare “mai hostato in USA” come regola di esclusione per cluster iraniani |
| Passaggio a **Cloudflare** dopo esposizione del shared IP | Nascondere origine dopo discovery | Hunting per hostname/DGA + JA3/comportamento, non solo IP di origin |

### E. Durante il downtime

| Segnale | Perché conta | Come usarlo |
|---------|--------------|-------------|
| **Certificati SSL ancora registrati** mentre il C2 è inattivo | Filo amministrativo vivo | Monitorare CT/cert per domini legacy anche in silenzio operativo |
| Downtime **molto più lungo** della baseline storica del gruppo | Possibile stress esterno (conflitto, blackout, loss of operators) oltre alla sola OPSEC | Correlare con timeline geopolitica senza affermare causalità |

---

## 3. Mini-regole per altri cluster

Quando guardi MuddyWater, OilRig, APT35, ecc., chiediti:

1. La footprint attuale è ancora della **stessa classe** (VPS vs shared, stesso tipo di pannello, stessi paesi)?  
2. C’è stato un **report forte** o un **evento geopolitico** nelle settimane precedenti un cambio?  
3. Cosa è **rimasto uguale** (tooling, path, Telegram, DGA) mentre cambiava l’hosting? Quello è il filo da seguire.  
4. L’IP nuovo è shared? Allora alza il peso di dominio + comportamento e abbassa il peso dell’IP isolato.  

---

## 4. Solido / ipotesi / sconosciuto

**Solido**  
- Sequenza IP/provider/pannello descritta da Semperis.  
- Timing spegnimento post-SafeBreach e ripresa post-downtime.  
- Uso di shared Namecheap USA per Tornado second-stage e successivo strato Cloudflare.

**Ipotesi**  
- Scelta USA come decisione consapevole di “ultimo posto in cui cercare” vs vincolo di disponibilità provider.  
- Stesso schema di migrazione verso shared adottato in parallelo da altri cluster iraniani (da verificare caso per caso).

**Sconosciuto**  
- Identità di registranti / payment path (fuori scope OSINT pubblico).  
- Se il downtime è dovuto a conflitto, a cautela OPSEC, a perdita di accesso, o a mix.

---

## 5. Collegamenti

- `analysis/prince-of-persia-detailed.md`  
- `iocs/prince-of-persia-2026.md`  
- `analysis/infrastructure-migration-method.md`  
- `analysis/starlink-channel-migration-case.md` (migrazione di *canale*, complemento a questa di *hosting/stack*)  

---

*Output del progetto infrastrutture: segnali, non solo IOC del caso PoP.*
