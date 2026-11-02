# Note operative per hunting di C2 via Starlink (focus cluster iraniani)

**Scopo:** trasformare l’osservazione “MuddyWater ha usato Starlink” in azioni di detection e investigazione concrete.

---

## 1. Cosa cambia rispetto al C2 tradizionale

| Aspetto classico | Con Starlink |
|------------------|--------------|
| Geolocalizzazione IP “sospetta” (Iran, VPS low-cost, ecc.) | L’IP di uscita può apparire in range SpaceX / gateway satellitari (spesso USA o altri paesi) |
| ASN “sporchi” o noti per abuse | ASN legittimi di SpaceX / satellite uplink |
| Pattern di beacon su porte non standard da VPS | Stesso beacon ma veicolato attraverso uplink satellitare |
| Blocco geografico efficace | Meno efficace; il traffico sembra “pulito” dal punto di vista geo |

**Conseguenza:** i playbook basati solo su GeoIP o su liste di paesi ad alto rischio perdono efficacia.

---

## 2. Segnali da cercare (in ordine di utilità)

### Priorità alta
- Traffico in uscita da host **non mobili / non autorizzati** verso ASN o range IP noti di SpaceX / Starlink uplink.
- Beacon o connessioni periodiche che coincidono temporalmente con:
  - periodi di blackout internet in Iran;
  - campagne MuddyWater già documentate (fine 2025 – inizio 2026).
- Presenza di tooling MuddyWater noto (RMM, Phoenix lineage, MuddyViper, ecc.) **insieme** a egress satellitare.

### Priorità media
- Uso di protocolli C2 già associati a MuddyWater (HTTP su porte non standard, raw TCP su 443, ecc.) ma con IP di destinazione in range satellitari.
- Host che improvvisamente iniziano a generare traffico verso gateway satellitari senza giustificazione business (es. workstation di ufficio fisse).

### Priorità contestuale
- Qualsiasi attività Telegram anomala correlata (Prince of Persia usa Telegram bot per exfil; MuddyWater ha storia di messaging abuse).
- Certificati o builder che appaiono sia in campioni MuddyWater sia in cluster MaaS criminali (angolo ibrido già segnalato).

---

## 3. Azioni pratiche raccomandate

1. **Aggiornare le watchlist ASN/IP**  
   Includere gli ASN e i range di uplink SpaceX/Starlink nei sistemi di monitoring egress (non per bloccarli in blocco, ma per alerting su host non autorizzati).

2. **Correlazione temporale**  
   Allineare i log di egress satellitare con le timeline pubbliche delle campagne MuddyWater e con i periodi di blackout/restrizioni internet in Iran.

3. **Baseline degli host**  
   Definire quali macchine nell’organizzazione hanno legittimamente bisogno di connettività satellitare. Tutto il resto è candidato a indagine.

4. **Non isolare il segnale**  
   Starlink da solo non attribuisce. Diventa forte solo in presenza di:
   - tooling noto;
   - RMM non autorizzato;
   - overlap con altre IOC del cluster;
   - timing coerente.

5. **Casi ransomware / access broker**  
   In incidenti che coinvolgono affiliate legati a Fox Kitten, verificare anche eventuali componenti di egress non tradizionale (satellitare incluso).

---

## 4. Limiti attuali delle fonti pubbliche

- Non sono ancora pubblici (al momento della stesura) fingerprint dettagliati di beacon specifici “Starlink-only” di MuddyWater.
- Non esistono liste esaustive e stabili di IP di uscita Starlink utili come IOC statici a lungo termine (la natura del servizio li rende dinamici).
- L’attribuzione resta dipendente da correlazione multi-sorgente.

---

## 5. Collegamenti interni al repository

- Profilo MuddyWater (sezione Starlink C2 e dual-use brand)
- `analysis/starlink-iranian-actors.md` (contesto strategico e dualità regime/operatori)
- `analysis/aggressive-research-agenda.md` (Fronte 1)
- `analysis/divergent-connections.md`

---

*Documento operativo. Aggiornare non appena emergono nuovi dettagli pubblici su beacon, ASN o campioni.*
