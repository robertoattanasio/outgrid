# outgrid

Outgrid is a CSS layout grid for pages that need both a readable content width and elements that can stretch to the edges of the screen. It uses custom properties for its global settings, and works as plain CSS or with an optional Tailwind CSS v4 entry.

Package: [npmjs.com/package/outgrid](https://www.npmjs.com/package/outgrid)

Documentation: [dev.robertoattanasio.com/outgrid](https://dev.robertoattanasio.com/outgrid)

## Installation

```sh
npm install outgrid
```

Once it’s installed, import the entry that matches your setup in your main stylesheet.

Plain CSS:

```css
@import "outgrid";
```

For Tailwind CSS v4, import Outgrid after Tailwind:

```css
@import "tailwindcss";
@import "outgrid/tailwind";
```

## API

Outgrid provides the grid and container, plus utilities for full-width breakouts and padding that follows the grid. You can find the details for each part here:

- [Custom properties](./docs/custom-properties.md)
- [og-grid](./docs/grid.md)
- [og-container](./docs/container.md)
- [Breakouts](./docs/breakouts.md): `og-full`, `og-content`, `og-start-full`, `og-end-full`
- [Bleed padding](./docs/bleed-padding.md): `og-pl-bleed`, `og-pr-bleed`, `og-px-bleed`
- [Tailwind CSS entry](./docs/tailwind.md)

## Scripts

For the available project scripts and what they do, see [docs/scripts.md](./docs/scripts.md).

## License

[MIT](./LICENSE)
