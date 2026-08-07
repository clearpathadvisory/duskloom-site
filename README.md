# duskloom.app

Static site. No build step, no framework, no analytics.

| Path | File | What |
|---|---|---|
| `/` | `index.html` | Landing page, with the app embedded and playable |
| `/app` | `app/index.html` | The real app — a copy of `duskloom-app/www/index.html` |
| `/privacy` | `privacy/index.html` | Privacy policy. This is the URL both stores require. |

## Deploying

Vercel builds nothing — it serves the files. Push to `main` and it redeploys.

## Keeping the app in sync

`app/index.html` is a copy. After any change to the app, replace it:

    cp ../duskloom-app/www/index.html app/index.html

## Before launch

- Replace `hello@duskloom.app` in `index.html` and `privacy/index.html` with the real address
- Swap the two placeholder store buttons in `index.html` for the official Apple and
  Google badge artwork, and point them at the real listings
- Add `og-image.png` (1200×630) and reference it with `<meta property="og:image">`

## A promise worth keeping

There is no analytics, no cookie banner and no third-party script here, because the
privacy page says the app collects nothing and the site should not quietly contradict
it. If you ever want traffic numbers, use Vercel's own server-side analytics rather
than a client-side tracker.
