# Breakouts

Classes for children of `og-grid` that reach the viewport edges, on both sides or one.

| Class           | Columns                         | Margins                          |
| --------------- | ------------------------------- | -------------------------------- |
| `og-full`       | `content-start` / `content-end` | `-var(--og-bleed)` on both sides |
| `og-content`    | `content-start` / `content-end` | `0`                              |
| `og-start-full` | starts at `content-start`       | `-var(--og-bleed)` at the start  |
| `og-end-full`   | ends at `content-end`           | `-var(--og-bleed)` at the end    |

## Behavior

- `og-full` spans the content, then negative margins push it out by `--og-bleed` on each side, to the viewport edges.
- `og-content` puts an element back on the content, cancelling `og-full`, for example at a breakpoint.
- `og-start-full` and `og-end-full` set only one edge: the other one is the element's own `grid-column-end` or `grid-column-start`, which by default is the content edge.
- Margins are logical (`margin-inline-start`, `margin-inline-end`): in right-to-left layouts the start is on the right.
- `--og-bleed` uses `100vw`, which includes the vertical scrollbar where it takes space: a full-bleed element can then overflow horizontally by half the scrollbar width.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<section class="og-grid">
  <img class="og-full" src="/cover.webp" alt="" />
  <img class="og-start-full" style="grid-column-end: col-end 6" src="/left.webp" alt="" />
  <p style="grid-column: col-start 8 / content-end">Text on the right</p>
</section>
```
