# China 2026 — Two Weeks, Seven Ways

A single-page, self-contained interactive feature comparing **seven 14-day China adventure
itineraries** (all 24 Oct – 6 Nov, all starting in Hong Kong + Shenzhen and flying home via a
Qatar Airways hub). Pick a trip and the whole page re-themes: hero, animated route map,
day-by-day timeline, activity gallery, animated costs, and a head-to-head comparison.

The seven routes:

1. **The Silk Road** — Gansu deserts, dunes & the Great Wall's wild west
2. **The Southern Karst** — Yangshuo climbing, Zhangjiajie & Chongqing
3. **The Yunnan Highlands** — Tiger Leaping Gorge, Shangri-La, rice terraces
4. **The Kham Frontier** — Chengdu pandas, Leshan/Emei & Daocheng Yading
5. **Roof of the World** — Lhasa to Everest Base Camp
6. **The Wild West** — Xinjiang: Kashgar, Turpan & the Karakoram
7. **Caves & Karst** — Guizhou: Getu climbing, Huangguoshu & ethnic villages

## Tech

- One file: [`index.html`](index.html). Inline CSS + vanilla JS. No build step, no framework.
- Fonts via Google Fonts CDN; photos hotlinked from Wikimedia Commons (license-clean), with a
  themed gradient placeholder as an automatic fallback if an image fails to load.
- The route map is a real, Mercator-projected China outline; pins are placed by true lat/long.
- Fully responsive / mobile-first; respects `prefers-reduced-motion`.

## Publish as a static page (GitHub Pages)

```sh
# create a repo on GitHub and push (needs the GitHub CLI, logged in)
gh auth login
gh repo create china-2026 --public --source=. --remote=origin --push
```

Then in the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch →
Branch: `main` / `/ (root)`**. Your site goes live at
`https://<your-username>.github.io/china-2026/`.

Any other static host works too (Netlify, Cloudflare Pages, Vercel) — just point it at this
folder; `index.html` is the entry point.

## Swapping media

Search terms for every photo/video are in the `/* ASSETS TO SWAP */` block at the top of
`index.html` and on each element's `data-search` attribute. Replace the URLs in the `PHOTOS`
map, or drop real video ids into the `data-video-id="TODO_YOUTUBE_ID"` gallery tiles.
