# duskloom.app

Marketing site. Static, no build step, no framework, no analytics.
**The app itself is not served here** — it ships through the App Store and Google Play
from the separate `duskloom-app` repo.

| Path | File | What |
|---|---|---|
| `/` | `index.html` | Landing page |
| `/privacy` | `privacy/index.html` | Privacy policy — the URL both stores require |
| `/shots/` | screenshots | Phone captures used in the gallery |

## Deploying

Vercel serves the files as they are. Push to `main` and it redeploys.

## Adding the rest of the screenshots

Render them from the app repo:

    node shots.js sounds colour timer breathe mixes

That writes captioned store frames to `duskloom-app/store/`, and the raw phone
captures to `/tmp/shots/`. The **raw** ones belong here — no caption bands. Copy them
in as `2-sounds.png`, `3-colour.png`, `4-timer.png`, `5-breathe.png`, `6-mixes.png`,
then add a `<figure>` for each in `index.html` where the comment marks the spot.

## Before launch

- Replace `hello@duskloom.app` in `index.html` and `privacy/index.html`
- Swap the two placeholder buttons for the official Apple and Google badge artwork and
  point them at the real listings
- Add `og-image.png` (1200×630) and reference it with `<meta property="og:image">`

## No trackers

No analytics, no cookie banner, no third-party scripts. The privacy page states the
app collects nothing, and the site should not quietly contradict it. If you want
traffic numbers, use Vercel's server-side analytics rather than a client-side tag.
