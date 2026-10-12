# Hype Ticketing — draft catalog mock

Samostalni frontend mock za razgovor o proizvodu. Sadrži lokalni draft katalog događaja proverenih na javnoj Hype Production stranici, AI vodič za preporuke po gradu i budžetu, i admin ekran za reviziju izvora.

## Pokretanje na Ubuntu-u

1. Raspakuj folder `hype-ticketing-cursor-project` u `~/Projects/` i preimenuj ga u `hype-ticketing-mock` ako želiš kraću putanju.
2. U terminalu pokreni:

   ```bash
   cd ~/Projects/hype-ticketing-mock
   python3 -m http.server 5173
   ```

3. Otvori `http://localhost:5173` u browser-u.
4. U drugom terminalu otvori projekat u Cursor-u:

   ```bash
   cursor ~/Projects/hype-ticketing-mock
   ```

Ako komanda `cursor` nije dostupna, izaberi **File → Open Folder** u Cursor-u i otvori folder projekta.

## Rad sa Codex-om u Cursor-u

U Codex panelu zalepi:

> Nastavi rad na Hype Ticketing mock-u kao vizuelnom demo katalogu. Zadrži lokalni draft import iz javnog izvora, jasno označi neverifikovane cene i slike, i nemoj dodavati checkout, plaćanje, rezervacije, realnu dostupnost ili backend.

## Izvor podataka

- Izvorna stranica: `https://www.hypeproduction.rs/koncerti/`
- Datum importa: `2026-10-12`
- Provera API/feed opcija: WordPress REST root postoji, ali nije pronađen upotrebljiv normalizovan event API/feed za javni import događaja. Katalog je zato lokalni snapshot, a ne browser-side scraper.
- Svi importovani događaji ostaju `draft` / `unverified` dok admin ne potvrdi cenu, venue, zone, kapacitet, dostupnost i pravo korišćenja slika.

## Granice mock-a

- Nema backend-a, GitHub remote-a, checkout-a, rezervacija, plaćanja ni stvarne prodaje ulaznica.
- Ne izmišljaju se cene, ticket zone, kapacitet ili dostupnost.
- Za vizuelni demo pretpostavljeno je odobrenje za reuse slika sa izvora. Posteri koriste postojeće `imageUrl` vrednosti, uz lazy loading i alt tekst; rezervni poster se prikazuje ako URL nedostaje ili slika ne može da se učita. Statusi `draft` / `unverified` ostaju nepromenjeni.
- Hype Ticketing vizuelni identitet još nije potvrđen; izgled u ovom mock-u je predlog.
