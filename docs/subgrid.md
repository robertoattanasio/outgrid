# og-subgrid

A child of `og-grid` that spans the frame and hands the grid's columns down to its own children: a section, a card, a list whose content stays on the columns of the page.

## Styles

| Property                | Value                |
| ----------------------- | -------------------- |
| `grid-column-start`     | `frame-start`        |
| `grid-column-end`       | `frame-end`          |
| `display`               | `grid`               |
| `row-gap`               | `var(--og-gutter-y)` |
| `grid-template-columns` | `subgrid`            |

## Behavior

- Its children are placed on the columns of the parent grid, with its gutter: `col-start 3`, `frame-end` and the other lines keep their names.
- Breakouts work inside it: `og-view`, `og-view-start` and `og-view-end` read `--og-frame-gap` from the parent grid and reach the view.
- The rows are its own: `row-gap` is `--og-gutter-y`, as in `og-grid`.
- It can be narrower than the frame: set its own `grid-column`, and its children use the columns it spans.
- Subgrids nest: an `og-subgrid` inside an `og-subgrid` keeps the same columns.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<main class="og-grid">
  <section class="og-subgrid">
    <h2 style="grid-column: col-start 1 / col-end 6">On columns 1 to 6</h2>
    <p style="grid-column: col-start 7 / frame-end">On 7 to the end</p>
    <img class="og-view" src="/band.webp" alt="" />
  </section>
</main>
```
