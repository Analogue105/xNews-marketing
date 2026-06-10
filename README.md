# xNews Marketing

Marketing site for xNews, built by a105.link.

## Stack

- SvelteKit + TypeScript
- Svelte 5 runes
- Skeleton UI + Tailwind CSS v4

## Local Development

```sh
npm install
npm run dev -- --open
```

## Scripts

```sh
npm run dev
npm run check
npm run build
npm run preview
```

## Project Structure

- `src/routes/+page.svelte`: page assembly, navigation, reveal behaviour
- `src/lib/components/marketing`: modular marketing sections
- `src/app.css`: global theme, layout, and motion styles

## Content Notes

- Use Australian English spelling in all user-facing copy.
- Keep messaging focused on returns, reconciliation, and inventory clarity.
- Brand context: xNews is operated by a105.link.

## Deploy

The project is configured for Vercel with `@sveltejs/adapter-vercel`.

### Vercel deployment

1. Import `Analogue105/xNews-marketing` into Vercel.
2. Keep build settings as defaults for SvelteKit.
3. Deploy from `main`.

For CLI deploys, install Vercel CLI and run:

```sh
vercel
```
