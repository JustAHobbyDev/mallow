# Mallow

A tiny, soft CSS micro-framework for quiet, content-first interfaces.

Mallow is classless-first: semantic HTML should look good on its own. A small
set of layout primitives and components is available when structure needs more
than HTML can express cleanly.

## Principles

- Semantic HTML before component classes.
- A small, intentional design-token vocabulary.
- Dark-first, low-contrast surfaces and restrained hierarchy.
- A few composable layout primitives instead of utility-class sprawl.
- No JavaScript, build step, or dependencies.

## Use

```html
<link rel="stylesheet" href="mallow.css">
```

Then write ordinary HTML:

```html
<main class="container">
  <article>
    <h1>Minimal interfaces</h1>
    <p>Semantic HTML should get you most of the way there.</p>
    <button>Continue</button>
    <button class="secondary">Cancel</button>
  </article>
</main>
```

Open `index.html` for a living specimen of the framework.

## API

### Tokens

Colors, typography, spacing, radii, and content width are exposed as custom
properties on `:root`.

### Semantic HTML

Mallow styles the common document and form elements directly, including:

`body`, headings, paragraphs, links, lists, code, blockquotes, tables, inputs,
selects, textareas, and buttons.

### Layout

- `.container` — centered reading-width container
- `.stack` — vertical flex layout with consistent gap
- `.cluster` — wrapping horizontal flex layout
- `.sidebar-layout` — responsive sidebar/content grid

### Components

- `.surface` — raised bordered surface
- `.card` — padded raised surface
- `button.secondary` — secondary button treatment
- `.muted` — muted text

## Status

Mallow is experimental. The goal is to discover the smallest useful API before
adding package tooling or a larger component vocabulary.

## License

Not selected yet.
