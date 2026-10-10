# Supported visuals and how to brief them
Supply page content in raw_data and visual choices in instructions/diagram.
The server agent creates editable canvas elements; clients need not generate
the complete document JSON. These are rendering capabilities, not extra MCP tools.

- Icons: native SVG elements resolve Iconify collection:name IDs, such as
  ph:lightning-bold or lucide:sun. Put the requested ID, meaning, color and
  placement in instructions. Use icons only where they clarify the content.
  Do not invent icon fields inside Mermaid or ECharts syntax.
- Diagrams: set page.diagram to the desired Mermaid family and arrangement,
  or include Mermaid source there. Put exact node labels, directed edges,
  actors, sequence order and relationship labels in raw_data. Requested
  diagrams use Mermaid; its node shapes are part of its supported grammar.
  Flowcharts support varied semantic shapes: rectangles for processes, rounded
  terminals, diamonds for decisions, cylinders for databases, parallelograms
  for input/output, subroutine boxes, circles, hexagons and document shapes.
  The frontend uses Mermaid 11.17+, including expanded flowchart node syntax
  such as decision@{ shape: diamond, label: "Approved?" } and
  report@{ shape: doc, label: "Report" }. Use consistent shapes for equivalent
  roles; do not decorate every node with an arbitrary different shape.
  Shape syntax depends on the diagram family: do not paste flowchart shapes
  into sequence, class or state diagrams. Mermaid icons/images require their
  own supported syntax and configured resources; native Iconify support does
  not mean every Mermaid family accepts arbitrary icon IDs.
- Native shapes: request cards, circles, rectangles, lines and decorative
  accents in instructions. They support composition around text and visuals.
- Custom SVG: request bespoke vector illustrations in instructions; supplied
  SVG markup can be included as source data. Prefer Iconify for known symbols.
  SVG is sanitized; scripts, event handlers and arbitrary interactive HTML
  are not a supported input contract. Do not use SVG to bypass diagram rules.
- Charts: ECharts-backed canvas charts. Supply categories/dates, exact series
  values, units, series names, and sources in raw_data. Request bar, line, pie,
  scatter or another suitable supported chart in instructions. State whether
  values are counts, percentages or currency; never infer missing numbers.
- Tables: provide explicit column names, rows, units and footnotes in raw_data,
  and request a readable table in instructions.
- Images: set page.image only when an image is needed, with subject, purpose
  and placement. Image generation/retrieval depends on enabled worker services;
  rendering support alone does not guarantee an image provider is configured.

Example chart source: {"categories":["Q1","Q2"],"unit":"USD",
"series":[{"name":"Revenue","values":[120000,165000]}]}.
Example diagram source: {"nodes":[{"id":"panel","label":"Solar panel"},
{"id":"inverter","label":"Inverter"}],
"edges":[{"from":"panel","to":"inverter","label":"DC electricity"}]}.

reasoning_effort controls the server generation agent, not the MCP client's
own thinking. Use low (default) for clear page-by-page briefs; none for simple,
fully specified changes; medium for synthesis or detailed visual composition;
high for difficult relationships or multi-constraint diagrams. Complete source
data does not remove layout and validation work. Model/provider support varies.
Lower effort can reduce work, but is not a price cap or quality guarantee.
Do not automatically increase effort and repeat a paid job after failure.
Credits are metered from actual usage, including work consumed before failure.

## Page sizes and themes
Set create_document.request.aspect_ratio to one of these exact values:
- 16:9: 1280x720, widescreen presentations and desktop.
- 4:3: 960x720, classic presentations and tablet viewing.
- 1:1: 1080x1080, square social carousels and infographics.
- 4:5: 1080x1350, portrait feed posts and social carousels.
- 9:16: 1080x1920, vertical stories and mobile presentations.
- a4-landscape: 1123x794, landscape reports.
- a4-portrait: 794x1123, printable one-pagers and reports.
One document has one shared size. Create separate documents for different
formats; mixed page sizes and custom dimensions are not exposed by this MCP
request schema. Editing preserves the existing document size.

State the theme in request.instructions: 'rabitmoon dark' (default),
'rabitmoon light', or an explicit brand palette with background/text/accent
colors. There is no separate theme field in the request schema. Keep colors,
typography, chart labels, diagram fills and connectors consistent across the
whole document, with sufficient contrast in both dark and light themes.
Compose for the chosen dimensions rather than scaling a landscape slide into
portrait. Stack content for 4:5 and 9:16, simplify crowded chart legends and
split long content into pages. Choose Mermaid LR/TB direction based on the
available diagram frame and label lengths; use TB for a long chain in a tall
narrow frame. Preserve readable labels, padding and safe margins.

Example: aspect_ratio="4:5", reasoning_effort="low", instructions="Create a
rabitmoon dark portrait carousel at 1080x1350. Stack one headline, one main
visual and one takeaway per page. Use orange primary and teal comparison
marks, light labels, and top-to-bottom diagrams where the frame is narrow."
