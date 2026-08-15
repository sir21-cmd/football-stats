# Varsity Football Stats

Play-by-play stat keeper for high school football. Works offline, keeps everything on the
device, and exports a MaxPreps entry sheet, a printable box score, season totals and CSV.

## Putting it online (GitHub Pages)

1. On GitHub, click **+ → New repository**. Name it something like `football-stats`,
   set it **Public**, and create it.
2. On the empty repo page, click **uploading an existing file**.
3. Drag in all six files from this folder — `index.html`, `sw.js`, `manifest.webmanifest`,
   `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — then **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**,
   **Branch: main**, **Folder: / (root)**, and **Save**.
5. Wait a minute, then open `https://YOUR-USERNAME.github.io/football-stats/`.

Adding it to an existing Pages site works too — every path in here is relative, so you can
drop these files into a subfolder (e.g. `/football/`) and it will run from there.

## Getting the icon on the iPad

Open the page in **Safari** (not Chrome — only Safari can install to the home screen on iOS),
tap the **Share** button, then **Add to Home Screen**. It opens full screen with no address bar.
Do this on every device that keeps stats.

The first load caches the whole app, so it keeps working with no signal. When you upload a new
version, devices pick it up the next time they open the app with a connection.

## Files

| File | What it is |
|---|---|
| `index.html` | The entire app — HTML, CSS and JavaScript in one file |
| `sw.js` | Service worker: caches the app so it runs with no signal |
| `manifest.webmanifest` | Name, colours and icons for the home-screen install |
| `icon-*.png`, `apple-touch-icon.png` | Home screen / launcher icons |

## Updating it later

Re-upload `index.html` (GitHub will ask to replace it). If you change `sw.js`, bump the
`VERSION` string at the top so every device clears its old cache.

## Where the data lives

In the browser's local storage on each device — no account, no server, nothing leaves the
device. **Back up after each game** from Setup → Back up everything. Clearing Safari's website
data will erase it.
