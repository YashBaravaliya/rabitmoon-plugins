---
name: plan-rabitmoon-visuals
description: Plan page-by-page rabitmoon layouts with appropriate charts, Mermaid diagrams, icons, SVG, themes and aspect ratios before submitting generation.
---

This skill plans a document; planning alone does not authorize a paid generation.
Read [visual capabilities](references/visuals.md) and [design guidance](references/design.md).
For the live supported schema use get_creation_guide when connected.

Map each page to one takeaway, supplied evidence and a dominant visual. For a
chart specify exact series, categories, units and sources. For Mermaid specify
the family, labelled nodes/edges and direction. Use semantic shapes: decisions
as diamonds, storage as cylinders, process rectangles, document shapes for
documents; expanded shapes apply to flowcharts, not every Mermaid family.

Specify Iconify collection:name identifiers for known symbols. Native shapes and
sanitized custom SVG can complement a layout. Do not invent image/diagram tool
names. Include image requirements only when needed and requested, with subject,
placement and purpose; image service availability must not be assumed.

Choose visuals proactively when they clarify the user's material. Use charts for
numeric comparisons, Mermaid for processes and relationships, icons for familiar
concepts, and custom SVG for bespoke explanatory illustrations (for example a
labelled solar panel, an energy pathway or a product cutaway). Prefer a concise
text layout when a visual would add clutter; do not force an illustration onto
every page or invent numbers to fill a chart.

In each page's instructions specify the visual's purpose, subject, placement,
relative size, labels, palette and relationship to the supplied facts. For custom
SVG, describe the scene and geometry; the generation agent can produce markup.
If exact SVG is supplied, put it in raw_data and explain its intended use in
instructions. Use self-contained vectors with a viewBox, readable strokes and
theme-compatible fills; omit scripts, external dependencies and embedded HTML.
Keep headings, body text and numerical charts as native editable elements where
possible rather than flattening the whole page into one SVG. These are directions
inside existing fields, not new tool arguments.

Example page instruction: “Use a custom SVG solar-panel illustration on the left
third, orange sunlight rays and a teal electricity path. Place the supplied
three-step explanation on the right as editable text. Add only the supplied
labels; use a dark background and leave clear space around the illustration.”

Choose one size per document: widescreen 16:9, classic 4:3, square 1:1, portrait
4:5 or 9:16, or a4-portrait/a4-landscape. Recompose for portrait instead of shrinking
landscape. Use one consistent dark, light or user-provided palette with readable
labels and contrast. Default brand orange #FF6808 and teal #2A9D99 support dark
#090D16 surfaces; preserve source numbers and avoid misleading chart scales.

Return a clear page brief with facts separated from layout directions. State
unresolved factual gaps and any presentation assumptions. For clear instructions,
recommend low reasoning; never describe it as a cost cap or guaranteed quality.
