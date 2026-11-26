# og-grid

The layout grid: its columns fill the frame, centered, capped at `--og-max-width`, padded by `--og-padding`, `--og-columns` of them.

## Styles

| Property                | Value                                                        |
| ----------------------- | ------------------------------------------------------------ |
| `width`                 | `100%`                                                       |
| `max-width`             | `calc(var(--og-max-width) + var(--og-padding) * 2)`          |
| `margin-inline`         | `auto`                                                       |
| `padding-inline`        | `var(--og-padding)`                                          |
| `display`               | `grid`                                                       |
| `column-gap`            | `var(--og-gutter-x)`                                         |
| `row-gap`               | `var(--og-gutter-y)`                                         |
| `grid-template-columns` | `--og-columns` columns of `minmax(0, 1fr)`, with named lines |

## Lines

```
[frame-start] [col-start] 1fr [col-end] [col-start] 1fr [col-end] … [frame-end]
```

| Line            |                                 |
| --------------- | ------------------------------- |
| `frame-start`   | the start edge of the frame     |
| `frame-end`     | the end edge of the frame       |
| `col-start <n>` | the start of column `n`, from 1 |
| `col-end <n>`   | the end of column `n`, from 1   |

## Behavior

- Every direct child spans the whole frame, from `frame-start` to `frame-end`, unless it sets its own `grid-column`.
- Styles sit under `:where()`: specificity 0, any class of the project overrides them.

## Example

```html
<section class="og-grid">
  <h2>Spans the frame</h2>
  <p style="grid-column: col-start 1 / col-end 6">Columns 1 to 6</p>
  <aside style="grid-column: col-start 8 / frame-end">Column 8 to the end</aside>
</section>
```
