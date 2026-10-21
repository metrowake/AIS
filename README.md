# Quaderno di Degustazione

App per il telefono che segue le due schede AIS: la scheda analitico-descrittiva (vista, naso, bocca, considerazioni finali) e la scheda a punteggio su 100, con diario e guida ai termini. È una pagina statica senza server: i vini restano salvati sul dispositivo e l'app funziona anche senza rete.

## Metterla online (una volta sola)

1. Unisci questo branch su `main`.
2. Il workflow in `.github/workflows/pages.yml` attiva Pages e pubblica da solo a ogni push su `main`.
3. Se la pubblicazione non parte, su GitHub apri **Settings → Pages** e in **Build and deployment** scegli **GitHub Actions**.
4. Dopo un minuto l'app è su **https://metrowake.github.io/AIS/**.

## Aggiungerla alla schermata Home

**iPhone**: apri l'indirizzo in Safari, tocca **Condividi** (il quadrato con la freccia), poi **Aggiungi alla schermata Home**.

**Android**: apri l'indirizzo in Chrome, menu **⋮**, poi **Installa app** (o **Aggiungi a schermata Home**).

Da lì in poi si apre a schermo intero, con la sua icona, e carica all'istante anche in cantina senza segnale.

## Dati e backup

I vini stanno nell'archivio del browser del telefono (IndexedDB), non in rete. Dal menu **⋯** della cantina puoi:

- salvare o condividere un backup `.json` (con le foto), per esempio su File, Drive o WhatsApp;
- scaricare la tabella `.csv` per Excel;
- importare un backup, anche quello esportato dal vecchio quaderno su claude.ai.

Per passare a un altro telefono basta esportare il backup e importarlo dall'altra parte.

## Aggiornare l'app

Ogni volta che modifichi `index.html` o gli altri file, alza `VERSION` in `sw.js` (per esempio da `qd-1.0.0` a `qd-1.0.1`) e `APP_VERSION` in `index.html`. Al primo avvio successivo l'app mostra "C'è una versione nuova" e si aggiorna al tocco.

## File

- `index.html`: tutta l'app (stile, dati AIS, logica).
- `sw.js`: service worker per l'uso offline e gli aggiornamenti.
- `manifest.webmanifest`: nome, colori e icone per l'installazione.
- `icons/`: icona dell'app nei formati richiesti da iOS e Android.
