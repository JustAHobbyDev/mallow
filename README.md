# Vernier

A small dark CSS micro-framework for precise, content-first interfaces.

Vernier is classless-first: semantic HTML should look good on its own. A small
set of layout, state, and report primitives is available when structure needs
more than HTML can express cleanly.

The visual direction is a digital chalkboard crossed with a technical instrument:
a pure black field, crisp typography, hairline structure, compact controls,
selective hard-edged depth, and a restrained terminal-inspired palette.

## Principles

- Semantic HTML before component classes.
- Information establishes hierarchy before containers do.
- Dark-first, flat fields, small radii, and visible structure.
- Depth is explicit: surfaces stay flat; cards, code panels, and buttons use crisp offset shadows.
- Metrophobic for prose; IBM Plex Mono for labels, identifiers, measurements, and state.
- Color communicates behavior, state, or consequence; taxonomy remains neutral.
- Tabular, short, clear, and concise beats decorative chrome.
- The stylesheet is the configuration.
- A few composable primitives instead of utility-class sprawl.
- No JavaScript, build step, theme engine, or required runtime dependencies.

## Use

```html
<link rel="stylesheet" href="vernier.css">
```

Vernier prefers Metrophobic and IBM Plex Mono but does not bundle or fetch them.
Load the fonts yourself if you want the intended type treatment; otherwise the
framework falls back to common sans-serif and monospace families. The specimen
page loads both fonts from Google Fonts for demonstration.

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

## Configuration

There is no separate Vernier configuration format. Override the custom properties
in CSS:

```css
:root {
  --content-width: 64rem;
  --color-link: #55b6c8;
}
```

The goal is to preserve a direct relationship between source and rendered output.
If changing Vernier requires a generator, DSL, or build system, the framework has
probably become too complicated.

## API

### Tokens

Colors, typography, spacing, radii, content width, and physical-depth tokens are
exposed as custom properties on `:root`.

The default palette is pushed toward dark terminal instrumentation rather than a
conventional product-UI palette: pure black, cool gray structure, high-contrast
cyan for navigation, bright green for active/healthy state, orange for stable
state, amber for warnings, bright red for faults, and violet for experimental
state.

- `--color-link` — links, navigation, and interactive focus
- `--color-success` — active, healthy, or OK state
- `--color-stable` — stable or settled state
- `--color-warning` — warning or degraded state
- `--color-danger` — fault or error state
- `--color-experimental` — experimental or unusual state

Depth is deliberately crisp rather than blurred:

- `--shadow-sm` — controls and compact raised panels
- `--shadow-md` — cards and more prominent bounded modules

### Semantic HTML

Vernier styles common document and form elements directly, including:

`body`, headings, paragraphs, links, lists, code, blockquotes, tables, inputs,
selects, textareas, buttons, and progress meters.

Links use cyan by default. Neutral structural elements remain gray rather than
borrowing a state color. Code blocks are raised technical panels with a hard
offset shadow.

### Layout

- `.container` — centered content container
- `.stack` — vertical flex layout with consistent gap
- `.cluster` — wrapping horizontal flex layout
- `.sidebar-layout` — responsive sidebar/content grid

### Annotation and state

- `.label` — compact uppercase technical label
- `.meta` — muted technical metadata
- `.numeric` — monospace tabular numeric content
- `.tag` — neutral bordered taxonomy label
- `[data-state="active"]` — green
- `[data-state="healthy"]` — green
- `[data-state="ok"]` — green
- `[data-state="stable"]` — orange
- `[data-state="warning"]` — amber
- `[data-state="degraded"]` — amber
- `[data-state="danger"]` — red
- `[data-state="error"]` — red
- `[data-state="experimental"]` — violet
- `[data-state="idle"]` — muted gray

Taxonomy does not receive a semantic color. Use `.tag` when a category or grouping
needs visible structure:

```html
<span class="tag">research</span>
```

The public API intentionally does not provide color-by-name helpers. If color has
no semantic job, prefer normal text, typography, rules, tags, or other non-color
structure.

### Reports

`dl.readout` is a compact key/value instrument readout using semantic `<dl>`
markup:

```html
<dl class="readout">
  <dt>Host</dt>
  <dd>anvil</dd>
  <dt>State</dt>
  <dd data-state="healthy">NOMINAL</dd>
  <dt>Latency p95</dt>
  <dd data-state="warning">183 ms</dd>
</dl>
```

Native `<progress>` elements are styled as hard-edged meters and can use
`data-state="warning"` or `data-state="danger"` when the meter itself represents
that state.

### Components

- `.surface` — bounded flat surface with no elevation
- `.card` — compact raised surface with a hard offset shadow
- `button` — hard-edged raised control with a pressed interaction
- `button.secondary` — secondary raised control treatment
- `.muted` — muted text

Most content should remain directly on the field. Elevation is reserved for
controls and bounded modules whose separation from the page carries meaning.

## Status

Vernier is experimental. The goal is to discover the smallest useful API before
adding package tooling or a larger component vocabulary.

## License

Apache License 2.0. See `LICENSE`.
