# ludovicsaas.info

My personal website, built with [Astro](https://astro.build) as a static site.

All text is in [`src/data/profile.ts`](src/data/profile.ts); the page layout is in
[`src/pages/index.astro`](src/pages/index.astro).

```sh
npm install
npm run dev      # local preview at http://localhost:4321
npm run build    # static output in dist/
```

`/cv.html` and `/contact.html` redirect to the matching sections so old links keep working.

## Deployment (Cloudflare)

Connect this repository in the Cloudflare dashboard (Workers & Pages → Create → Import a repository) with:

- Build command: `npm run build`
- Output directory: `dist`

The Node version used for the build is pinned in `.node-version`. `wrangler.jsonc` lets Cloudflare
deploy the `dist/` folder as static assets, and `npx wrangler deploy` does the same from this machine.
