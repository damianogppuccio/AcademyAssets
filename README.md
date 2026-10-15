# Funnel prova gratuita eLearning Academy – beta

Due funnel separati, uno per prodotto, ciascuno con tre pagine:

| Prodotto | Ingresso | Form | Ringraziamento |
|---|---|---|---|
| Genya | `genya/index.html` | `genya/form.html` | `genya/grazie.html` |
| Arca Evolution | `arca/index.html` | `arca/form.html` | `arca/grazie.html` |

`index.html` nella cartella principale è solo un indice per la presentazione: non fa parte del funnel.

## Pubblicazione su GitHub Pages (beta)

1. Carica il contenuto di questa cartella nel repository (oppure in una sottocartella).
2. Vai in Settings → Pages, scegli il branch `main` e la cartella `/ (root)`.
3. I link diventano `https://<utente>.github.io/<repo>/genya/` e `.../arca/`.

Nella beta il form non invia e non salva dati. Controlla solo che i campi siano compilati, poi apre la pagina di ringraziamento. Tutte le pagine hanno `noindex`, quindi non finiscono su Google.

## Passaggio a Pardot

1. **Asset.** Carica in Pardot (Content → Files) i file di `assets/` e aggiorna i percorsi `../assets/...` nelle pagine con gli URL che Pardot ti restituisce.
2. **Form.** In `form.html` sostituisci tutto il blocco fra `PARDOT FORM: INIZIO` e `PARDOT FORM: FINE` con il form Pardot (codice iframe, oppure `%%content%%` se usi un layout template). Il form ha i campi Nome, Cognome, Email e Cellulare, più i consensi privacy, e un campo nascosto `prodotto` (Genya / Arca Evolution).
3. **Completion action.** Imposta il redirect a `grazie.html` del funnel corrispondente.
4. **Link della notifica in-product.** Usa un custom redirect Pardot diverso per Genya e per Arca, così i clic vengono contati separatamente.
5. **Indicizzazione.** Rimuovi `<meta name="robots" content="noindex,nofollow">` solo se le pagine devono essere indicizzate.

## Da sostituire prima del go-live

- `assets/img/hero-genya.jpg` e `assets/img/hero-arca.jpg` sono ritagli a bassa risoluzione presi da uno screenshot. Vanno sostituiti con le foto originali, mantenendo lo stesso nome del file.
- `assets/img/wk-logo-stacked.png` e `wk-globe.png` vanno sostituiti con il logo ufficiale WK (meglio in SVG), se Marketing lo fornisce.

## Asset

- Font: Fira Sans, licenza SIL OFL (`assets/fonts/OFL-LICENSE.txt`), incluso nei file del pacchetto.
- Icone: dal Pack_Icone_2026 WK, versione con anello colorato, esportate in SVG.
- Colori WK: Rosso `#E5202E`, Verde `#85BC20`, Blu `#007AC3`.
