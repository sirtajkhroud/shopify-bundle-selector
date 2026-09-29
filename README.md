# Shopify Bundle Selector

A custom single / duo bundle purchase UI for a Shopify product page, built for
[Mulberry Silks](https://mulberrysilks.co) to **replace a paid bundling app**.
Vanilla Liquid, HTML, and JavaScript — no dependencies, no app subscription.

## Demo

Open **`demo/index.html`** in any browser to try it with sample data (cart
actions are stubbed). Or enable GitHub Pages on this repo for a live link.

## What it does

- **Single vs. Duo toggle** — Duo bundles two pillowcases at 25% off, shown with
  a live strike-through of the original price.
- **Per-item colour & size** — each item in the bundle picks its own colour and
  size independently (mix and match).
- **Custom colour dropdown** — a built-from-scratch accessible select with colour
  swatches, replacing the native `<select>` for a consistent look.
- **Live pricing** — totals and the bundle discount recompute as selections change.
- **AJAX add-to-cart & buy-now** — adds all bundle items in one request via the
  Shopify Cart API (`/cart/add.js`) without a page reload.
- **Variant matching** — resolves each colour/size choice to the right Shopify
  variant ID from titles in the form `"Colour / Size"`.

## Files

| File | Purpose |
|------|---------|
| `bundle-selector.liquid` | The production Shopify snippet (real code from the live theme). |
| `demo/index.html` | Standalone browser demo with sample data and a stubbed cart. |

## Using it in a Shopify theme

1. Add `bundle-selector.liquid` to your theme's `snippets/` and render it inside
   your product form: `{% render 'bundle-selector' %}`.
2. Adjust the colour list, size labels, and the two size variables to match your
   product's options and variant naming (`"Colour / Size"`).
3. Requires the Shopify AJAX Cart API (standard on Online Store 2.0 themes).

## Notes

Extracted from the live production theme. Product data, images, and variant IDs
live in Shopify; the snippet reads them at render time.
