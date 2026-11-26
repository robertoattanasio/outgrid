# Custom properties

The whole grid is set up through custom properties, declared on `:root`.

| Property         | Default                                                           |                                                   |
| ---------------- | ----------------------------------------------------------------- | ------------------------------------------------- |
| `--og-columns`   | `12`                                                              | number of columns                                 |
| `--og-max-width` | `80rem`                                                           | width of the frame, without the padding           |
| `--og-padding`   | `1rem`                                                            | space between the frame and the viewport edges    |
| `--og-gutter-x`  | `clamp(0.5rem, 2.2vw, 2rem)`                                      | gap between columns                               |
| `--og-gutter-y`  | `clamp(0.5rem, 2.2vw, 2rem)`                                      | gap between rows                                  |
| `--og-frame-gap` | `max(var(--og-padding), calc((100vw - var(--og-max-width)) / 2))` | distance from the frame edge to the viewport edge |

## Behavior

- Override them on `:root` to change every grid, or on a single element to change that one and what's inside it.
- `--og-frame-gap` is computed, not meant to be set. `og-grid` computes it again on itself, so it follows overrides of `--og-max-width` and `--og-padding` set on the grid.
- `--og-frame-gap` assumes the grid is as wide as the viewport and centered.

## Example

```css
:root {
  --og-max-width: 72rem;
  --og-padding: clamp(1rem, 4vw, 3rem);
}

@media (width < 48rem) {
  :root {
    --og-columns: 4;
  }
}
```
