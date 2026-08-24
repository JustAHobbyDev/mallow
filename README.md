# Mallow

A small dark CSS micro-framework for precise, content-first interfaces.

Mallow is classless-first: semantic HTML should look good on its own. A small
set of layout primitives and annotations is available when structure needs more
than HTML can express cleanly.

The visual direction is a digital chalkboard crossed with a technical instrument:
a near-black field, crisp typography, hairline structure, compact controls,
selective hard-edged depth, and bright color used sparingly to communicate
function or state.

## Principles

- Semantic HTML before component classes.
- Information establishes hierarchy before containers do.
- Dark-first, flat fields, small radii, and visible structure.
- Depth is explicit: surfaces stay flat; cards, code panels, and buttons use crisp offset shadows.
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

Colors, typography, spacing, radii, content width, and physical-depth tokens are
exposed as custom properties on `:root`.

Color tokens are semantic rather than generic accents:

- `--color-link` — links, navigation, and interactive focus
- `--color-success` — active, healthy, or OK state
- `--color-warning` — warning or degraded state
- `--color-category` — category and grouping labels
- `--color-experimental` — experimental or unusual state

Depth is deliberately crisp rather than blurred:

- `--shadow-sm` — controls and compact raised panels
- `--shadow-md` — cards and more prominent bounded modules

### Semantic HTML

Mallow styles common document and form elements directly, including:

`body`, headings, paragraphs, links, lists, code, blockquotes, tables, inputs,
selects, textareas, and buttons.

Links are blue by default. Neutral structural elements remain gray rather than
borrowing a state color. Code blocks are treated as raised technical panels with
a hard offset shadow.

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

- `.surface` — bounded flat surface with no elevation
- `.card` — compact raised surface with a hard offset shadow
- `button` — hard-edged raised control with a pressed interaction
- `button.secondary` — secondary raised control treatment
- `.muted` — muted text

Most content should remain directly on the field. Elevation is reserved for
controls and bounded modules whose separation from the page carries meaning.

## Status

Mallow is experimental. The goal is to discover the smallest useful API before
adding package tooling or a larger component vocabulary.

## License

Apache License 2.0. See `LICENSE`.
