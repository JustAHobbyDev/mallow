# Mallow

A small dark CSS micro-framework for precise, content-first interfaces.

Mallow is classless-first: semantic HTML should look good on its own. A small
set of layout primitives and annotations is available when structure needs more
than HTML can express cleanly.

The visual direction is a digital chalkboard crossed with a technical instrument:
a near-black field, crisp typography, hairline structure, compact controls, and
bright color used sparingly to communicate function or state.

## Principles

- Semantic HTML before component classes.
- Information establishes hierarchy before containers do.
- Dark-first, flat surfaces, small radii, and visible structure.
- IBM Plex Sans for prose and IBM Plex Mono for labels, identifiers, measurements, and state.
- Color communicates function or state; it is not generic emphasis.
- A small, intentional design-token vocabulary.
- A few composable layout primitives instead of utility-class sprawl.
- No JavaScript, build step, or required runtime dependencies.

## Use

```html
<link rel="stylesheet" href="mallow.css">
```

Mallow prefers IBM Plex Sans and IBM Plex Mono but does not bundle or fetch them.
Load the fonts yourself if you want the intended type treatment; otherwise the
framework falls back to common sans-serif and monospace families. The specimen
page loads IBM Plex from Google Fonts for demonstration.

Then write ordinary HTML:

```html
<main class="container">
  <p class="label">System / Status</p>
  <h1>Collector</h1>
  <p>Semantic HTML should get you most of the way there.</p>

  <p class="numeric" data-state="active">● ACTIVE / 12.4 events/s</p>
  <p><a href="/logs">Open logs</a></p>
</main>
```

Open `index.html` for a living specimen of the framework.

## API

### Tokens

Colors, typography, spacing, radii, and content width are exposed as custom
properties on `:root`.

Color tokens are semantic rather than generic accents:

- `--color-link` — links, navigation, and interactive focus
- `--color-success` — active, healthy, or OK state
- `--color-warning` — warning or degraded state
- `--color-category` — category and grouping labels
- `--color-experimental` — experimental or unusual state

### Semantic HTML

Mallow styles common document and form elements directly, including:

`body`, headings, paragraphs, links, lists, code, blockquotes, tables, inputs,
selects, textareas, and buttons.

Links are blue by default. Neutral structural elements remain gray rather than
borrowing a state color.

### Layout

- `.container` — centered content container
- `.stack` — vertical flex layout with consistent gap
- `.cluster` — wrapping horizontal flex layout
- `.sidebar-layout` — responsive sidebar/content grid

### Annotation and state

- `.label` — compact uppercase technical label
- `.meta` — muted technical metadata
- `.numeric` — monospace tabular numeric content
- `[data-state="active"]` — green
- `[data-state="healthy"]` — green
- `[data-state="ok"]` — green
- `[data-state="warning"]` — orange
- `[data-state="degraded"]` — orange
- `[data-state="experimental"]` — lime
- `[data-state="idle"]` — muted gray
- `[data-category]` / `.category` — pink category or grouping label

The public API intentionally does not provide `data-accent="blue"` or similar
color-by-name helpers. If color has no semantic job, prefer normal text,
typography, rules, or other non-color structure.

### Components

- `.surface` — bounded flat surface
- `.card` — compact padded surface
- `button.secondary` — secondary button treatment
- `.muted` — muted text

## Status

Mallow is experimental. The goal is to discover the smallest useful API before
adding package tooling or a larger component vocabulary.

## License

Apache License 2.0. See `LICENSE`.
