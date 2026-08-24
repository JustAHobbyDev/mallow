# Changelog

All notable changes to Vernier will be documented in this file.

## [0.1.0] - 2026-08-24

Initial release.

### Added

* Dark, high-contrast visual system for technical and content-first interfaces.
* Pure black field with restrained terminal- and instrument-inspired colors.
* Metrophobic for prose and headings.
* IBM Plex Mono for labels, identifiers, measurements, numeric values, and machine state.
* Semantic state colors:

  * green for active, healthy, and OK
  * orange for stable
  * amber for warning and degraded
  * red for danger and error
  * violet for experimental
  * gray for idle and neutral state
* Cyan links and interactive focus treatment.
* Neutral, visibly structured `.tag` styling for taxonomy and grouping.
* Crisp offset shadows for raised elements without blurred elevation.
* Hard-edged buttons with pressed-state movement.
* Raised code panels.
* Flat `.surface` and elevated `.card` primitives.
* Classless styling for common semantic HTML elements.
* Layout primitives:

  * `.container`
  * `.stack`
  * `.cluster`
  * `.sidebar-layout`
* Technical presentation helpers:

  * `.label`
  * `.meta`
  * `.numeric`
* `dl.readout` for compact key/value instrument readouts.
* Styled native `<progress>` meters with semantic warning and danger states.
* Tables, forms, blockquotes, lists, inline code, and images.
* Responsive behavior for sidebar layouts and readouts.
* Reduced-motion handling for button interactions.
* CSS custom properties for palette, typography, spacing, geometry, layout, and physical depth.

### Design principles

* Semantic HTML before component classes.
* Information establishes hierarchy before containers do.
* Color communicates function, state, or consequence rather than generic emphasis.
* Taxonomy communicates through structure rather than color.
* Flat fields by default; elevation is reserved for controls and bounded modules.
* Tabular, short, clear, and concise presentation over decorative chrome.
* The stylesheet is the configuration.
* No JavaScript, build system, theme engine, or required runtime dependencies.

### Status

Vernier `0.1.0` establishes the initial visual language and API.

The next phase is to use Vernier in real projects and let those applications determine which primitives deserve to remain, change, or expand.

