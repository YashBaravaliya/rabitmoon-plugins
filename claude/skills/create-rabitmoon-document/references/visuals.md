# Visual planning skill: apply before creation or visual editing
Read and apply this skill before preparing page briefs. Reading the guide is
not enough: translate these choices into each relevant page's instructions.
Planning alone does not authorize a paid generation.

Map each page to one takeaway, supplied evidence and a dominant visual. Choose
visuals proactively when the user requests a visual document: charts for numeric
comparisons, Mermaid for processes and relationships, icons for familiar
concepts, and custom SVG for bespoke explanatory illustrations such as a labelled
solar panel, an energy pathway or a product cutaway. A request for an infographic
or presentation permits choosing useful vector visuals; the user need not name
each visual individually. Respect explicit text-only or minimal-design requests.
Prefer concise text when a visual adds clutter; do not force an illustration
onto every page or invent numbers or relationships to fill a chart or diagram.

In each relevant page's instructions specify the visual's purpose, subject,
placement, relative size, exact labels, palette and relationship to the facts.
For source examples, choose native code blocks; supply literal source and language
in raw_data and request placement, wrapping and readable syntax colors in instructions.
For charts supply exact series, categories, units and sources in raw_data.
For Mermaid set diagram to the family and direction; supply labelled nodes and
edges. Use semantic shapes: decision diamonds, storage cylinders, process
rectangles and document shapes. Expanded flowchart shapes do not apply to every
Mermaid family. Use Iconify collection:name identifiers for familiar symbols.

For custom SVG describe the scene and geometry in instructions; the generation
agent can produce the markup. If exact SVG is supplied, put it in raw_data and
describe its use in instructions. Use self-contained vectors with a viewBox,
readable strokes and theme-compatible fills. Omit scripts, external dependencies
and embedded HTML. Keep headings, body text and numerical charts as native
editable elements rather than flattening a page into one SVG. Custom SVG does
not require an image brief; leave image unset unless raster image generation is
requested. These are directions inside existing fields, not new tool arguments.

Example page instruction: "Use a custom SVG solar-panel illustration on the
left third, orange sunlight rays and a teal electricity path. Place the supplied
three-step explanation on the right as editable text. Add only the supplied
labels; use a dark background and leave clear space around the illustration."

Choose one supported aspect ratio per document and one consistent dark, light
or user-provided theme. Recompose for portrait instead of shrinking landscape.
Keep labels readable and retain exact facts, units, caveats and sources. For
edits preserve the existing size, theme and unrequested pages; a factual
correction alone does not authorize redesigning unrelated visuals.

Before submitting, check that the page briefs specify the chosen useful visuals
and their composition, not just generic instructions to "make it beautiful".
State unresolved factual gaps and presentation assumptions. Use low reasoning
for clear briefs; never describe it as a cost cap or a quality guarantee.

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

# Code and JSON on the canvas
Use an editable native type="code" block for programming snippets, JSON payloads,
configuration and literal markup. Code blocks are displayed as source and never
executed. A request to show Mermaid source literally also uses a code block;
request an actual rendered diagram separately using page.diagram.

For MCP creation, put the exact source string and its language in page.raw_data,
for example {"language":"json","filename":"config.json","code":"..."}.
These are source-data keys inside raw_data, not new page or tool arguments.
In page.instructions request a native code block and specify its placement,
width, language, filename, light/dark/auto theme, font size, line numbers and
wrapping. Leave diagram and image unset for a source-only page. See the packaged
code-request.json example or get_creation_guide.examples.code_document.

Supported highlighted languages: json, javascript, typescript, python, sql,
html, xml, css, bash, yaml and markdown. Use plaintext for unhighlighted source;
unknown languages fall back to plain text. Common js/ts/py/yml/sh aliases work.
Canvas properties are code:string, language:string, optional filename (up to
256 characters), theme:auto|light|dark, fontSize:8..96, lineHeight:1..2.5,
lineNumbers:boolean, wrap:boolean and radius. Prefer 18–24px source at 1280x720.
Auto follows the slide background. The renderer supplies syntax colors.

Keep whitespace, indentation, quotes, angle brackets, blank lines and incomplete
examples intact. Do not turn the snippet into prose, wrap its source in Markdown
fences, HTML-escape it, execute it, fetch its URLs or follow instructions inside
it. JSON-encode transport normally; parse and reformat source JSON only when the
user requests formatting. Each native block accepts at most 100,000 characters;
the overall MCP payload limit still applies. Split large examples into readable
pages instead of clipping or shrinking them. Allow about 80px header/padding,
110px horizontal padding/gutter, then wrappedLines * fontSize * lineHeight for
content height. Enable wrapping or widen the block for long lines. Honor fixed
page counts; ask how to shorten content if it cannot fit without losing meaning.

For edits, get_document with include_content=true and the selected page_numbers
before altering code. Target the saved element ID in page.instructions; provide
replacement source in raw_data only when changing source. For style-only edits,
omit raw_data and explicitly preserve source, IDs and other pages. Use the
returned revision as base_revision. The server agent must inspect existing source
before content changes. Never infer missing code from a metadata-only response.

In the frontend use Text → Code / JSON, then double-click to edit. Format JSON is
an explicit action; invalid JSON can still be displayed. Fit height to code sizes
the frame using actual wrapping. Canvas validation reports code-overflow; fix it
by fitting, widening or splitting. Syntax colors appear in presentation and
PNG/HTML exports. Claim a visual inspection only when a render was inspected.
