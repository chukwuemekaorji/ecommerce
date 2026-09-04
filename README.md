# Nexus Global Business — Gift Catalog

A static, single-page mockup of a corporate gift catalog. Browse a grid of
products, click into a product to see a full gallery view. No backend, no
cart, no checkout — this is a concept/demo site, not a functioning store.

**Live site:** https://ecommerce-delta-brown-58.vercel.app

## What's here

- `index.html` — the entire site (markup, styles, and logic in one file).
  Vanilla HTML/CSS/JS, no build step, no dependencies.
- `images/` — product photos, plus the header logo (`logo-full.png`).
- `temu-links.csv` — reference list mapping each product to the Temu listing
  it was sourced from. Not used by the site itself; this is a private lookup
  for whoever's managing the catalog.

## Running locally

No build step needed. From the project root:

```bash
python3 -m http.server 8765
```

Then open `http://localhost:8765`.

## Adding or editing a product

Products are defined in a single array near the bottom of `index.html`:

```js
const products = [
  { id: "unique-id", name: "Display Name", image: "images/photo.jpg" },
  ...
];
```

- `id` is used for routing (`#/product/<id>`) — keep it unique and URL-safe.
- `image` should point to a file in `images/`.
- Order in the array is the display order in the grid.
- The product detail page reuses the same image four times as gallery
  thumbnails (placeholder behavior until real variant photos exist per
  product).

## Deployment

The `main` branch is connected to Vercel; pushing to `main` auto-deploys to
the live URL above. No separate build/deploy step is required.
