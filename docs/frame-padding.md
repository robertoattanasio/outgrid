# Frame padding

Classes that pad an element by `--og-frame-gap`, so its box reaches the view while its content stays on the frame.

| Class                | Property                                    |
| -------------------- | ------------------------------------------- |
| `og-pad-frame`       | `padding-inline: var(--og-frame-gap)`       |
| `og-pad-frame-start` | `padding-inline-start: var(--og-frame-gap)` |
| `og-pad-frame-end`   | `padding-inline-end: var(--og-frame-gap)`   |

## Behavior

- On a full-width element, outside any grid, the content starts and ends where the frame does.
- On an `og-view` element, the background reaches the edges and the content stays on the frame.
- Padding is logical: in right-to-left layouts the start is on the right.
- Styles sit under `:where()`: specificity 0.

## Example

```html
<section class="og-grid">
  <div class="og-view og-pad-frame" style="background: black">On the frame, background to the edges</div>
</section>

<footer class="og-pad-frame">On the frame, no grid needed</footer>
```
