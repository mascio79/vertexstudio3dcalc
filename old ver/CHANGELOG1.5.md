# 3DCALC — Calcolatore Costi Stampa 3D — Changelog

---

## v1.5 · Maggio 2026

### Nuove funzionalità
- **Gestione revisioni automatica** — snapshot automatico ad ogni salvataggio; fino a 5 revisioni conservate in localStorage; ripristino con un click dalla sezione Revisioni; modal di conferma con preview dati; export singola revisione come `.json`; pulsante salvataggio manuale immediato
- **Tema chiaro/scuro** — toggle ☀️/🌙 in topbar e nella sidebar (sezione Sistema); preferenza salvata in localStorage; tema chiaro con palette alternativa su sfondo grigio chiaro

### Modifiche
- Sidebar: aggiunta voce Revisioni (🕓) nella sezione Sistema
- Topbar: aggiunto pulsante toggle tema

---

## v1.4 · Maggio 2026

### Nuove funzionalità
- **Layout unificato responsive** (stile Spartans Manager) — unico file `3d-calc.html` che sostituisce i precedenti file desktop e mobile separati; sidebar fissa collassabile su desktop con toggle ◀/▶; hamburger ☰ + overlay su tablet/mobile; topbar con titolo dinamico per pagina; drive bar in fondo che segue la sidebar; breakpoint 1100px / 900px / 640px / 400px; su mobile il riepilogo costi appare sopra i campi di input

### Modifiche
- Eliminati `3d-calc-desktop.html` e `3d-calc-mobile.html`, sostituiti da `3d-calc.html`
- Navigazione spostata in sidebar con sezioni Calcolatore / Configurazione / Archivio / Sistema
- Topbar con pulsanti Esporta e Reset contestuale

---

## v1.3 · Maggio 2026

### Nuove funzionalità
- **Sincronizzazione Google Drive** (singola utenza) — login OAuth Google con schermata di accesso al primo avvio; salvataggio automatico su Drive 2 secondi dopo ogni modifica; polling live ogni 30 secondi con notifica aggiornamento da altro dispositivo; barra di stato in basso con pallino colorato (grigio / giallo pulsante / verde / rosso); token salvato in localStorage per sessioni successive; rilevamento sessione scaduta con re-login; opzione "Continua senza Google Drive" per uso solo locale; pulsante cambio account
- **IVA configurabile** — campo IVA% (default 22%) nella sezione riepilogo; prezzo di vendita mostrato sia IVA esclusa (verde) che IVA inclusa (arancio) con importo IVA a parte; compatibile con regimi agevolati (4%, 10%) e vendite estero (0%)

### Modifiche
- Sezione Sync rielaborata: mostra stato connessione Drive e istruzioni
- Export/Import JSON mantenuti come backup aggiuntivo nella sezione Sync e nella sidebar

---

## v1.2 · Maggio 2026

### Nuove funzionalità
- **Export / Import JSON** — pulsante "Scarica backup.json" scarica un file con stampanti, filamenti e storico; pulsante "Importa" carica un file esportato su un altro dispositivo; dati salvati in chiave unificata `3dc2_db` con migrazione automatica dalle vecchie chiavi separate; compatibile tra versione desktop e mobile

### Modifiche
- Tab Sync aggiunta a entrambe le versioni (desktop e mobile) con istruzioni passo-passo
- localStorage: migrazione da chiavi separate (`3dc2_profiles`, `3dc2_filaments`, `3dc2_history`) a chiave unificata `3dc2_db`

---

## v1.1 · Maggio 2026

### Nuove funzionalità
- **Ammortamento calcolato automaticamente** — nella scheda stampante: campi Costo acquisto, Costo aggiuntivo, Vita stimata (anni), Manutenzione annuale (€/anno), Uptime %, Consumo energetico (W), Costo elettricità (€/kWh); badge arancio mostra in tempo reale il €/h calcolato e le ore/anno stimate; formula: `(acquisto + extra + manutenzione × anni) / (anni × 8760h × uptime%)`
- **Fattore efficienza materiale** — moltiplicatore per sprechi (supporti, brim, purghe); default 1.1 (+10%)
- **Fattore buffer** — margine di sicurezza sul costo totale; default 1.0
- **Icona stampante FDM SVG stilizzata** — sostituisce l'emoji 🖨️; presente nel logo, nei tab, nei pulsanti e nelle schede profilo; disegnata con telaio cubico, barra X-axis, testina, ugello e piano di stampa
- **Pillole personalizzabili** — stampanti e filamenti nel calcolatore mostrati come pillole con × per rimuovere e ＋ per aggiungere; nessun popup per la rimozione
- **Caratteri ingranditi (versione mobile)** — tutti i font aumentati di ~15%: label 10→12px, input 14→15px, bottoni 14→16px, totale 38→42px

### Modifiche
- Rimosso badge "Offline" dall'header
- Default stampanti: solo Bambu Lab A1 Mini (rimossi Ender 3, Bambu X1C, Prusa MK4, Bambu P1S)
- Scheda stampante: aggiunto campo Costo elettricità (€/kWh) separato per profilo

### Fix
- `saveAll()` non veniva chiamata prima della prima inizializzazione dati
- Funzione `showPage` non aggiornava correttamente il tab attivo della sidebar su navigazione diretta

---

## v1.0 · Marzo 2026 — Versione iniziale

### Funzionalità base
- **Calcolatore costi FDM** — materiale (costo per grammo da costo bobina e peso bobina), elettricità (da wattaggio stampante e tariffe), manodopera (tariffa oraria × tempo), ammortamento (€/h configurabile), imballaggio e spedizione, costi fissi mensili ripartiti, percentuale fallimenti
- **Produzione in serie** — quantità pezzi e pezzi per piatto; ottimizzazione automatica numero piatti per costi macchina
- **Slider margine profitto** — 0–200%; prezzo di vendita suggerito aggiornato in tempo reale
- **Grafico donut interattivo** — suddivisione percentuale dei costi con legenda cliccabile
- **Profili stampante** — salvataggio multiplo con nome, wattaggio e ammortamento orario; pillole cliccabili nel calcolatore
- **Libreria filamenti** — salvataggio con nome, tipo, colore, costo e peso bobina; pillole cliccabili nel calcolatore
- **Storico preventivi** — fino a 100 voci con data, materiale, costo totale, prezzo vendita e margine
- **Persistenza dati** — localStorage come storage primario
- **UI** — dark mode, font Syne + Space Mono, animazioni, tooltip informativi, toast notifications
- **Versioni separate** — `3d-calc-desktop.html` per PC, `3d-calc-mobile.html` ottimizzata per Android con bottom nav e font touch-friendly

---

*3DCALC — Vertex Studio Bari*
