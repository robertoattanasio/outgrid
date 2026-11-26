# Tailwind CSS entry

`outgrid/tailwind` declares the same classes as Tailwind CSS utilities.

```css
@import "tailwindcss";
@import "outgrid/tailwind";
```

## Differences from the plain CSS entry

|                   | `outgrid`   | `outgrid/tailwind`                          |
| ----------------- | ----------- | ------------------------------------------- |
| Custom properties | on `:root`  | on `:root`, in `@layer base`                |
| Classes           | plain rules | `@utility`, in Tailwind's `utilities` layer |
| Variants          | no          | yes: `md:og-view`, `hover:og-frame`         |
| Generated         | always      | only the classes the project uses           |

## Behavior

- Needs Tailwind CSS v4: it's an optional peer dependency.
- The rules inside each utility sit under `:where()`: specificity 0, like the plain entry. A Tailwind utility on the same property wins: `px-6` overrides the padding of `og-pad-frame`, so set one or the other.
- The custom properties are set the same way: on `:root` or on any element, with plain CSS or arbitrary properties such as `[--og-columns:4]`.

## Example

```html
<section class="og-grid [--og-columns:4] md:[--og-columns:12]">
  <img class="og-view md:og-frame" src="/cover.webp" alt="" />
</section>
```
