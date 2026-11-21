# og-container

The width of `og-grid` without the grid: centered, capped at `--og-max-width`, padded by `--og-padding`.

## Styles

| Property         | Value                                               |
| ---------------- | --------------------------------------------------- |
| `width`          | `100%`                                              |
| `max-width`      | `calc(var(--og-max-width) + var(--og-padding) * 2)` |
| `margin-inline`  | `auto`                                              |
| `padding-inline` | `var(--og-padding)`                                 |

## Behavior

- Its content lines up with the content of any `og-grid`.
- It doesn't compute `--og-bleed` on itself: breakouts inside it read the value from `:root`.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<header class="og-container">…</header>
```
