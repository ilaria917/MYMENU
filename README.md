# 🍷 TavoloFacile

App web per la gestione di un ristorante, pensata per **tablet e palmari**: meno lavoro per i camerieri, sala e cucina più coordinate, cantina sempre sotto controllo.

Nessuna dipendenza e nessuna fase di build: è un unico file `index.html` (HTML, CSS e JavaScript).

## Funzionalità

| Scheda | Cosa fa |
|---|---|
| **Sala** | Mappa dei tavoli con stato (libero, occupato, da servire), comande con + e −, conto parziale, conferma degli ordini arrivati dai clienti. |
| **Cucina** | Comande in colonne (Nuove, In preparazione) con tempo trascorso e stimato, numero di cuochi regolabile. |
| **Cantina** | Giacenze di bevande e vini scalate in automatico a ogni ordine confermato, soglie minime, avviso "Da riordinare", carico merce. |
| **Cliente** | Menu digitale da QR code sul tavolo: il cliente ordina da solo e vede lo stato e l'attesa stimata. L'ordine parte solo dopo la conferma del cameriere. |
| **Menu** | Aggiunta di piatti e vini, "Finito oggi" (blocca gli ordini), "Togli dal menu" (fine stagione), etichetta "stagione". |

**Tempo di attesa:** minuti di preparazione già in coda, divisi per i cuochi attivi, più il tempo del nuovo piatto.

## Uso in locale

```bash
git clone https://github.com/<tuo-utente>/tavolofacile.git
cd tavolofacile
# apri index.html nel browser, oppure:
python3 -m http.server 8000   # poi vai su http://localhost:8000
```

## Pubblicazione su GitHub Pages

1. Carica il progetto su GitHub (branch `main`).
2. Vai su **Settings → Pages** e come *Source* scegli **GitHub Actions**.
3. Ad ogni push su `main` il workflow `.github/workflows/pages.yml` pubblica il sito.

## Dati e limiti attuali

- I dati (ordini, scorte, menu) sono salvati nel `localStorage` del browser, chiave `tf1`. Restano sul dispositivo in cui si usa l'app.
- Non c'è login né ruoli: chiunque apra l'app può modificare il menu e le scorte.
- Menu, prezzi e tempi sono d'esempio: si modificano nell'array `MENU` all'inizio dello script.

## Idee per i prossimi passi

- [ ] Archivio condiviso (backend) per sincronizzare tablet, palmari e telefoni dei clienti
- [ ] Accesso con PIN per ruolo (cucina, sala, responsabile)
- [ ] Stampa della comanda e riepilogo incassi giornaliero
- [ ] QR code diverso per ogni tavolo
- [ ] Logo e colori personalizzabili

## Licenza

MIT, vedi [LICENSE](LICENSE).
