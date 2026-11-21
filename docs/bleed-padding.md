# Bleed padding

Classes that pad an element by `--og-bleed`, so its content lines up with the grid while its box reaches the viewport edges.

| Class         | Property                                |
| ------------- | --------------------------------------- |
| `og-pl-bleed` | `padding-inline-start: var(--og-bleed)` |
| `og-pr-bleed` | `padding-inline-end: var(--og-bleed)`   |
| `og-px-bleed` | `padding-inline: var(--og-bleed)`       |

## Behavior

- On a full-width element, outside any grid, the content starts and ends where the grid content does.
- On an `og-full` element, the background reaches the edges and the content stays on the grid.
- Padding is logical: in right-to-left layouts the start is on the right.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<section class="og-grid">
  <div class="og-full og-px-bleed" style="background: black">Aligned with the grid, background to the edges</div>
</section>

<footer class="og-px-bleed">Aligned with the grid, no grid needed</footer>
```
