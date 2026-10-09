# CSS Architecture

## Files

```
css/
  main.css            entry point: layer order + @imports
  01-tokens.css       custom properties and user preferences
  02-reset.css        browser-default normalization
  03-base.css         bare-element defaults
  04-layout.css       containers, bands, grid patterns
  05-components.css   reusable UI components
  06-utilities.css    single-purpose helpers
  07-states.css       interaction states and dark mode
  08-print.css        print styles
```

## Cascade layers

`main.css` sets the order: `@layer reset, base, layout, components, utilities, states;`
Later layers win regardless of specificity, so a component style isn't overridden by a more specific base rule like `a:visited`.

## Tokens

All colors, spacing, type, and focus styles are custom properties in `01-tokens.css`, such as `--color-band-hero`, `--color-accent`, and `--color-accent-on-dark` (added to pass contrast). Components use tokens instead of hard-coded values, so dark mode only has to override tokens.

## Naming

- Components: BEM-style (`.timeline__item`, `.card__title`)
- Utilities: `.u-` prefix (`.u-skip-link`)
- States: `.is-` prefix (`.is-current`) or native pseudo-classes

## Components

Nav (CSS-only hamburger), button, card, window card, polaroid, timeline, skill tile, form field, footer, callout.

## Responsive layout

- Logical properties (`inline-size`, `margin-block-start`) instead of left/right/top/bottom
- `.cluster` and `.skill-grid` use `repeat(auto-fit, minmax(min(100%, …), 1fr))`, so they reflow without breakpoints
- Cards use subgrid so their links line up, with an `@supports` fallback
- `.card` uses a container query to place its header side by side at 380px+
- Breakpoints: 48rem for the hero split and nav, 64rem for extra padding

## Dark mode and preferences

- Dark mode: `body:has(#theme-toggle-input:checked) .site` overrides the color tokens. Without `:has()`, the toggle does nothing and the page still works.
- `prefers-reduced-motion` removes transitions.
- `prefers-contrast: more` thickens the focus ring and adds card borders.

## AI disclosure

Claude helped organize the CSS architecture and styling and explain CSS syntax. I reviewed the code and tested the site myself.
