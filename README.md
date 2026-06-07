# sciencepetr.com

A clean, minimal single-page personal site built with [Astro](https://astro.build).
Sections: About, Videos, and Contact — with a deep-blue link-hover effect and a
gentle swirling background.

## Run it locally

You need [Node.js](https://nodejs.org) 18 or newer.

```
npm install      # first time only
npm run dev      # preview at http://localhost:4321
```

Edit files and the preview updates instantly. When ready:

```
npm run build    # outputs the finished site to dist/
```

## Where things live

```
src/
  pages/index.astro     # the whole page (hero, about, videos, contact)
  layouts/BaseLayout.astro
  components/Header.astro, Footer.astro
  styles/global.css     # all styling (colors, fonts, swirl, hover splotch)
public/favicon.svg
```

## Personalize

- **About text** — the About section in `src/pages/index.astro`
- **Videos** — the `videos` array at the top of `src/pages/index.astro`.
  Set `embed` to a YouTube video ID (the part after `v=`) to embed it;
  leave it `""` to show a placeholder tile.
- **Links** — the `links` array in the same file.
- **Colors** — `--blue` and `--blue-deep` at the top of `src/styles/global.css`.
- **Font** — `--font` in `global.css` (currently Helvetica).
- **Swirl** — the `.bg-swirl` block in `global.css`; adjust `opacity`,
  `blur`, or animation durations to taste. It auto-disables for visitors who
  prefer reduced motion.

## Deploy to Vercel

1. Push this folder to a GitHub repository.
2. vercel.com → New Project → import the repo. Astro is auto-detected; deploy.
3. Project → Settings → Domains → add `sciencepetr.com` and `www.sciencepetr.com`.
4. Add the DNS records Vercel shows you in **Cloudflare** (DNS → Records) —
   typically an A record for the apex and a CNAME for `www`.
   Leave your MX records untouched so email keeps working.

## Deploy to Netlify

1. Push to GitHub.
2. netlify.com → Add new site → import the repo.
   Build command `npm run build`, publish directory `dist`.
3. Domain management → add `sciencepetr.com`, set the DNS records in Cloudflare.
