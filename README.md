# Card Vault

A phone app that scans your Pokémon cards, finds them in a free card database,
and keeps your collection **on your phone only**. Your cards can be grouped by
type, how rare they are, value, or set.

Everything is free:
- **Reading the card** happens on the phone (Tesseract, a free text reader). No photo ever leaves the phone.
- **Card info, pictures and prices** come from TCGdex, a free card database. No account or key needed.
- **Your collection** is saved inside the phone's browser. Nobody else can see it.

## Files

| File | What it does |
|---|---|
| `index.html` | The whole app: screens, camera, card reading, lookups, collection |
| `manifest.json` | Lets the phone install it like a real app (icon, name) |
| `sw.js` | Lets the app open even without internet |
| `icon.svg`, `icon-192.png`, `icon-512.png` | The app icon |

## Putting it on the phone (free, about 10 minutes)

Phones only allow the camera on a secure (https) web address, so the app needs
to live on a free website. GitHub Pages is free and easy:

1. Make a free account at **github.com** (a parent account is fine).
2. Click **+ → New repository**. Name it `card-vault`, choose **Public**, tick **Add a README**, click **Create**.
3. Click **Add file → Upload files**, drag in all the files from this folder, click **Commit changes**.
4. Go to **Settings → Pages**. Under *Branch* choose `main` and `/ (root)`, click **Save**.
5. After a minute the address appears at the top, like `https://YOURNAME.github.io/card-vault/`.

The website only holds the app itself. The collection is never uploaded, it
stays in his phone's browser.

### Install it on the phone
- **iPhone (Safari):** open the address, tap **Share → Add to Home Screen**.
- **Android (Chrome):** open the address, tap **⋮ → Add to Home screen / Install app**.

Always open it from the home-screen icon. The collection is tied to that
browser on that phone.

## What's in the app
- **Scan**: camera scanning, plus **Quick scan** (adds each card straight away and keeps the camera open, with an Undo button).
- **My cards**: group by type, how rare, value or set; sort and search.
- **Sets**: a progress bar for every set (e.g. 48 of 165), tap one to see which cards are still missing.
- **Pokédex**: every Pokémon by generation; shadows light up when you own a card of them. 5 different cards of one Pokémon earns a ★.
- **Stats**: total value, most valuable cards, types, rarity and value by set.
- **⚙️ Settings** (top right): dark or light mode, colour, card size, prices, backups.

## How to scan well
- Good light, no glare: tilt the card a little if the shiny part reflects.
- Card flat, filling the yellow box, straight on.
- The scanner reads the **card number at the bottom** (like `025/165`) and the **name at the top**.
  The number does most of the work.
- Tap the matching picture to confirm, pick the version (normal / reverse holo / holo), then **Add**.
- Full-art, gold or very shiny cards can be hard to read. Use **Search by name** for those
  (adding the number, like `25` or `25/165`, makes it exact).

## Good to know
- **Prices** come from US (TCGplayer) and European (Cardmarket) shops and are converted to
  Australian dollars using the rates in Settings. They're a guide to what a card is worth,
  not an exact offer. Tap **Update all prices** now and then.
- **Backups:** if the phone's browser data is cleared, the collection goes with it.
  Use **Settings → Save backup** once in a while.
- Only English cards for now.

## Ideas to try next
- Change the colours at the top of `index.html` (look for `--accent`).
- Add a "wish list" for cards he wants.
- Add a "duplicates" view to find cards to trade.
- Show how many cards of each set he has, e.g. "151: 48 of 165".
