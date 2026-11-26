# outgrid

A CSS layout grid with full-bleed breakouts, set up globally through custom properties. Public package on npm.

## Docs

- [README.md](./README.md): install, links to the docs.
- [docs/](./docs/): one file per group of classes, the custom properties and the Tailwind CSS entry, plus [scripts.md](./docs/scripts.md) and [release.md](./docs/release.md).

Read the relevant doc before changing the package. When a class or a property changes, update its doc in the same change.

## Structure

```
src/
  grid.css       the plain CSS entry, "outgrid"
  tailwind.css   the Tailwind CSS v4 entry, "outgrid/tailwind"
docs/
```

## Conventions

- The two entries declare the same custom properties and the same classes, with the same declarations. A change to one is made to the other in the same change.
- In `grid.css` a class is a plain rule. In `tailwind.css` it's an `@utility` and the custom properties sit in `@layer base`.
- Every selector is wrapped in `:where()`: specificity 0.
- Custom properties are prefixed `--og-`, classes `og-`.
- Everything is set through custom properties: no hard-coded size in a class.
- `og-grid` recomputes `--og-frame-gap` on itself, so overrides set on the grid apply.
- Inline properties are logical: `margin-inline`, `padding-inline-start`.
- No build, no JavaScript. Tailwind CSS is an optional peer dependency.
- No comments in the code unless asked.
