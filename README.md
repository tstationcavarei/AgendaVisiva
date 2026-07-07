# Agenda Visiva

App di agenda visiva per la pianificazione di attività quotidiane — pensata per l'uso in orizzontale su smartphone e tablet, con supporto per pittogrammi, timer e modalità di esecuzione guidata.

**Versione:** 1.0.0

## Come pubblicarla su GitHub Pages

1. Crea un nuovo repository su GitHub (es. `agenda-visiva`).
2. Carica **tutti** i file di questo zip nella root del repository:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `icon-192-maskable.png`
   - `icon-512-maskable.png`
3. Vai su **Settings → Pages** del repository.
4. In "Source" seleziona il branch `main` (o `master`) e cartella `/ (root)`.
5. Salva. Dopo circa un minuto l'app sarà raggiungibile all'indirizzo:
   `https://TUO-USERNAME.github.io/agenda-visiva/`

## Come installarla su Android

1. Apri l'indirizzo sopra con **Chrome** su Android.
2. Apparirà un banner "Aggiungi a schermata Home" (o menu ⋮ → "Installa app").
3. Una volta installata, si comporta come un'app nativa: icona in home, apertura fullscreen, funziona anche offline.

## Come aggiornarla in futuro

1. Modifica `index.html` (o altri file) nel repository GitHub.
2. **Importante:** apri `sw.js` e incrementa il numero di versione nella riga:
   ```js
   const CACHE_NAME = 'agenda-visiva-v1.0.1';  // <-- cambia qui ad ogni release
   ```
   Questo è ciò che dice al telefono "c'è una versione nuova, scaricala".
3. (Opzionale ma consigliato) Aggiorna anche `APP_VERSION` dentro `index.html`
   (cercare `const APP_VERSION='1.0.0';`) così il numero mostrato nelle
   Impostazioni → Info corrisponde alla release reale.
4. Fai commit e push su GitHub.
5. Sui dispositivi dove l'app è già installata, l'utente apre
   **Impostazioni → Info → 🔄 Aggiorna**: l'app scarica la nuova versione
   e si ricarica automaticamente. Il controllo avviene anche in automatico
   ogni volta che l'app viene riaperta con connessione internet attiva.

## Struttura dei file

```
index.html                  — l'intera app (HTML+CSS+JS in un unico file)
manifest.json                — metadati PWA (nome, icone, orientamento forzato)
sw.js                        — service worker: cache offline + meccanismo di aggiornamento
icon-192.png                 — icona 192×192
icon-512.png                 — icona 512×512
icon-192-maskable.png        — icona 192×192 "maskable" (Android adattivo)
icon-512-maskable.png        — icona 512×512 "maskable" (Android adattivo)
```
