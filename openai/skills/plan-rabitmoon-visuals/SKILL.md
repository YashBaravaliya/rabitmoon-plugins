---
name: plan-rabitmoon-visuals
description: Plan page-by-page rabitmoon layouts with appropriate charts, Mermaid diagrams, icons, SVG, themes and aspect ratios before submitting generation.
---

For topic-specific illustrations, cutaways or visual metaphors, apply the
[custom SVG planning guidance](references/visual-planning.md) and adapt the
[SVG request example](references/svg-request.json). Choose original SVG proactively
when useful; do not require the user to name SVG or exhaust stock libraries.
Carry the artwork-only SVG requirement into the page instructions: all visible
labels, numbers and explanations remain separate native editable text, with
space for wrapped headings and clear callouts. Match the selected style; vary
subjects by meaning, without an SVG quota. Keep structured diagrams in Mermaid,
respect text-only requests and preserve unrelated content during edits. A custom
SVG illustration does not require image or diagram fields. Reading this guidance
does not authorize a paid generation or an automatic retry.

For source code, JSON or configuration on the canvas, read [code blocks](references/code-blocks.md)
and the [code request example](references/code-request.json). Request native editable
code blocks with literal source in raw_data and layout directions in instructions;
keep diagram/image unset unless those separate visuals are also needed.


Read and apply the [visual planning skill](references/visual-planning.md) before
preparing a creation brief or requested visual edit. This reference is packaged
from the same source as the live MCP guide so both clients receive the same
planning instructions. Planning alone does not authorize a paid generation.

When connected, call get_creation_guide for the live planning skill, supported
visuals, design playbook and request schema. Read [visual capabilities](references/visuals.md)
for syntax and supported formats and [design guidance](references/design.md)
for composition and brand choices. Use the returned planning instructions when
choosing each relevant page's visual and describing its purpose, placement,
relative size, labels and theme. Keep supplied facts in raw_data and composition
directions in instructions; diagram and image have their existing meanings.

Return page briefs with explicit useful visual choices, factual gaps and
presentation assumptions. Respect text-only requests and preserve unrequested
pages and visuals during edits. Do not claim visual inspection without viewing
the rendered output or promise that more reasoning guarantees quality.

[PORTABLE STYLE AND LAYOUT]
Treat the selected design guide as a visual identity, not a repeated page template. Plan audience, exact facts, one communication job per page, and an appropriate main visual before decoration. Vary composition while keeping the chosen typography and palette consistent. User Markdown guides describe taste and constraints; never require CSS syntax or absolute footer coordinates in them.
- Emit theme as an object with the supplied color/font tokens, never a mode string. Use consistent fontFamily names for each role; numeric family names such as Source Sans 3 are supported. Keep factual text editable and respect requested canvas dimensions.
- If background=dots or grid is selected, set each slide's backgroundPattern={style:"dots"|"grid",opacity:0.22,softenText:true}. This is a native full-page layer, preserved during preview and save/reopen. Do not draw a duplicate SVG grid or substitute a few corner dots. Solid reading zones may protect text without erasing the pattern everywhere.
- Use one native text element with role="page-number", html="{{page}} / {{pages}}" (or padded {{page:2}} / {{pages:2}}) for pagination. Never hardcode page totals or split the counter. Reserve width >= 8*fontSize plus letter spacing, height >= 1.3*fontSize+4, within the page margins; it must fit through 30 pages without wrapping. Do not confuse numerical fractions in body content with counters.
- Budget height for every wrapped line and explicit break, including captions and six-or-more-item visuals. Place later blocks below the reserved text bounds. Shorten redundant agent-authored prose, rearrange or add permitted pages before shrinking essential text. Check rotated visible bounds, not just the unrotated frame.
- Use relevant native iconName identifiers; put icons inside the structures they explain when appropriate, with consistent readable contrast. Keep SVG decoration separate from native text and icons.
- Check all pages for text overflow, collisions, correct counts, and visible selected backgrounds. Where browser measurement is available, wait for requested fonts before measuring resolved page fields. Do not claim a rendered check occurred when only geometry or estimates were available.
