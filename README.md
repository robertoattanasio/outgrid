# outgrid

A CSS layout grid with full-bleed breakouts and a global setup through custom properties. Plain CSS, with an optional Tailwind CSS v4 entry.

Package: [npmjs.com/package/outgrid](https://www.npmjs.com/package/outgrid)

Documentation: [dev.robertoattanasio.com/outgrid](https://dev.robertoattanasio.com/outgrid)

## Install

```sh
npm install outgrid
```

Import it once, in your entry stylesheet:

```css
@import "outgrid";
```

With Tailwind, import the Tailwind entry instead, after Tailwind itself. The classes are the same, registered as utilities, so variants like `md:` and `hover:` work on them:

```css
@import "tailwindcss";
@import "outgrid/tailwind";
```

Import one or the other. The plain stylesheet sits outside Tailwind's cascade layers, and CSS outside a layer always wins over CSS inside one.

## Usage

`og-grid` centres the columns, caps them at the max width and pads the sides. Everything inside is a regular CSS grid with named lines, so you place items with the grid you already know:

```html
<div class="og-grid">
  <img class="og-full" />
  <aside class="sidebar">…</aside>
  <main class="content">…</main>
</div>
```

```css
.sidebar {
  grid-column: col-start 1 / col-end 3;
}

.content {
  grid-column: col-start 4 / content-end;
}
```

The lines are `content-start` and `content-end` around the columns, and `col-start N` and `col-end N` around column N. With Tailwind, `col-span-6`, `col-start-4` and `grid-cols-subgrid` work as they are.

## Classes

| class                                         | what it does                                                       |
| --------------------------------------------- | ------------------------------------------------------------------ |
| `og-grid`                                     | the grid: centred, capped at the max width, padded on both sides   |
| `og-container`                                | the width and padding of the grid, without columns                 |
| `og-full`                                     | edge to edge of the screen                                         |
| `og-start-full` / `og-end-full`               | bleeds off the left / right edge only                              |
| `og-content`                                  | back to the content area; cancels any bleed                        |
| `og-pl-bleed` / `og-pr-bleed` / `og-px-bleed` | padding as wide as the bleed, to bring content back on the columns |

Bleeding is a negative margin as wide as `--og-bleed`, so it works from any column and at any depth.

## Setup

Everything is a custom property. Set them once on `:root`, after the import:

```css
:root {
  --og-columns: 12;
  --og-max-width: 80rem;
  --og-padding: 1rem;
  --og-gutter-x: 2rem;
  --og-gutter-y: 2rem;
}
```

`--og-bleed`, the distance from the content area to the edge of the screen, is computed from these: read it, don't set it.

## Approach

- **Your classes win.** Every rule is wrapped in `:where()`, so any class on the same element overrides it, whatever the order.
- **Placement is not reinvented.** The library sets up the grid and the bleed; columns and rows are placed with plain CSS grid.
- **One setup.** A handful of custom properties drive every grid on the page.

## License

[MIT](./LICENSE).
