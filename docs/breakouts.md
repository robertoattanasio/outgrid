# Breakouts

Classes for children of `og-grid` that leave the frame for the view: they reach the viewport edges, on both sides or one. `og-frame` brings them back.

| Class           | Columns                     | Margins                              |
| --------------- | --------------------------- | ------------------------------------ |
| `og-view`       | `frame-start` / `frame-end` | `-var(--og-frame-gap)` on both sides |
| `og-view-start` | starts at `frame-start`     | `-var(--og-frame-gap)` at the start  |
| `og-view-end`   | ends at `frame-end`         | `-var(--og-frame-gap)` at the end    |
| `og-frame`      | `frame-start` / `frame-end` | `0`                                  |

## Behavior

- `og-view` spans the frame, then negative margins push it out by `--og-frame-gap` on each side, to the viewport edges.
- `og-frame` puts an element back on the frame, cancelling a breakout, for example at a breakpoint.
- `og-view-start` and `og-view-end` set only one edge: the other one is the element's own `grid-column-end` or `grid-column-start`, which by default is the frame edge.
- Margins are logical (`margin-inline-start`, `margin-inline-end`): in right-to-left layouts the start is on the right.
- `--og-frame-gap` uses `100vw`, which includes the vertical scrollbar where it takes space: an element on the view can then overflow horizontally by half the scrollbar width.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<section class="og-grid">
  <img class="og-view" src="/cover.webp" alt="" />
  <img class="og-view-start" style="grid-column-end: col-end 6" src="/left.webp" alt="" />
  <p style="grid-column: col-start 8 / frame-end">Text on the right</p>
</section>
```
