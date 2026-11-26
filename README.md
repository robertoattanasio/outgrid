# outgrid

Outgrid is a CSS layout grid for pages that need both a readable content width and elements that can stretch to the edges of the screen. It uses custom properties for its global settings, and works as plain CSS or with an optional Tailwind CSS v4 entry.

Package: [npmjs.com/package/outgrid](https://www.npmjs.com/package/outgrid)

Documentation: [outgrid.robertoattanasio.com](https://outgrid.robertoattanasio.com)

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

Two words name the two widths Outgrid works with. The **frame** is the readable width of the content: centred, capped at `--og-max-width`, kept off the edges by `--og-padding`. The **view** is the full width of the screen. Outgrid provides the grid and the container, which hold the frame, classes that take an element out to the view, and padding that brings its content back to the frame. You can find the details for each part here:

- [Custom properties](./docs/custom-properties.md)
- [og-grid](./docs/grid.md)
- [og-subgrid](./docs/subgrid.md)
- [og-container](./docs/container.md)
- [Breakouts](./docs/breakouts.md): `og-view`, `og-view-start`, `og-view-end`, `og-frame`
- [Frame padding](./docs/frame-padding.md): `og-pad-frame`, `og-pad-frame-start`, `og-pad-frame-end`
- [Tailwind CSS entry](./docs/tailwind.md)

## Scripts

For the available project scripts and what they do, see [docs/scripts.md](./docs/scripts.md).

## License

[MIT](./LICENSE)
