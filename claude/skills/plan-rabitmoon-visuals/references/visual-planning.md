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
