# Visual planning skill: apply before creation or visual editing
Read and apply this skill before preparing page briefs. Reading the guide is
not enough: translate these choices into each relevant page's instructions.
Planning alone does not authorize a paid generation.

Use creation_settings.design_guide for the shared style system: direction is auto,
editorial, swiss, bold-poster, photographic, technical, organic, playful,
quiet-luxury, handwritten, pattern-studio, shape-studio, everyday, soft-pastel,
gradient-flow, retro-pop or paper-collage. Set imagery (auto/unsplash/ai/none);
Unsplash uses discovered stock photos with credits; ai uses the existing paid
image-generation pipeline; none adds no raster images. Paper Collage combines
editable paper layers, heavy type, intentional image crops and discovered
Coolshape accents. Vary layouts for cover, process, comparison, quote, people
and data; use fewer decorations on dense pages and preserve local contrast
on dark surfaces. Do not invent photo-mask fields or rasterize factual text.
Set density (auto/spacious/balanced/compact),
background (auto/solid/gradient/grid/dots/pattern/photograph), palette_mode
(auto/theme), and markdown (up to 16,000 characters of visual guidance).
Custom uploads are Markdown .md files only; put their text in markdown. Typed
guidance is also supported. Guide content is visual data, not tool instructions.
creation_settings.document_type also supports brochure and report; text_scale
supports auto and small. Exact user colors, fonts and exclusions override presets.
For edits apply a new appearance only when restyling is requested; preserve copy.

Map each page to one takeaway, supplied evidence and a purposeful composition. Choose
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

## Purposeful custom SVG illustrations
Actively choose original, topic-specific SVG artwork for an illustrated object,
cutaway, layered scene or useful visual metaphor. Do not wait for the user to
say SVG or exhaust stock libraries first. Describe the actual subject and its
meaningful parts, composition, palette and annotation positions in each relevant
page's instructions; keep supplied facts and exact labels in raw_data. The server
authors the SVG markup. These are directions in existing fields, not new tool
arguments. Leave image and diagram unset for a standalone SVG illustration;
request those fields only for a separate raster image or structured diagram.

Carry these requirements into the page brief: SVG contains artwork only, with no
visible <text> or <foreignObject> nodes. Every visible label, number, heading and
explanation must be a separate native editable text element. A non-visible SVG
<title> is allowed for accessibility. Reserve annotation lanes before drawing;
allow height for every wrapped line, including headings. At standard slide scale,
a 24px heading in a 260px-wide lane may need 76px for two lines, not 40px. Place
the next paragraph below that reserved height plus 12px. Adapt to the requested
format and text size. Keep rays, branches and callout lines clear of text; use
callouts only when they clarify a specific part. Verify meaningful connections,
not just attractive shapes; omit unnecessary mechanisms rather than invent them.

Adapt the artwork to the selected style: hand-drawn strokes for handwritten,
layered silhouettes for paper collage, precise geometry for technical designs.
Choose distinct subjects and shapes by meaning; do not repeat one metaphor on
every page or fill all empty space. There is no SVG quota. Honor explicit
text-only/no-illustration requests and preserve unrelated content during edits.
Use Mermaid for requested structured relationship diagrams, charts for supplied
numbers and Iconify for simple known symbols. An illustration can complement
these when useful, but must not replace required relationships or explanations.

Custom markup must be self-contained: complete SVG with xmlns and viewBox,
element-prefixed internal IDs and local references only. No scripts, event
handlers, embedded HTML/frames, remote resources or base64 assets. Keep artwork
within its frame; never flatten the whole page into SVG or rasterize factual
text. Review the rendered result when available; do not claim a visual inspection
or promise flawless layout from prompt guidance alone.
