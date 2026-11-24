---
name: edit-rabitmoon-document
description: Update selected pages in an existing rabitmoon document using its current revision, preserving other pages and reporting job status and credits.
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


Use list_documents to help locate the user's document when needed, then
get_document with include_content=true and selected page_numbers to obtain the
actual document_id, revision and page content. Do not infer document ownership
from a URL or use another account. Read those pages before deciding changes;
request missing facts only when the saved content cannot answer them.

Read the actual visual metadata before restyling shapes, Coolshapes, patterns or
icons. Preserve their native element type, shapeId, palettePreset, custom colors,
noise settings, patternRecipe, iconName/iconWeight/iconColor and SVG markup unless
the requested change affects them. Existing artwork may use a category excluded
from new AI suggestions; preserve it rather than substituting a different shape.
Use the live visual guide for library capabilities and never render internal
clipboard/document JSON as visible text in place of the visual.

Read get_creation_guide and apply its visual planning skill to the requested
visual changes before preparing the request. Submit edit_document with base_revision from the latest
read, a new idempotency_key, and only the pages the user asked to change. Preserve
the document size, identity, page order and unrequested pages. Put exact changed
facts in raw_data and visual directions in instructions. Use low reasoning for
clear changes, or none for a simple fully specified edit.
For instruction-only changes raw_data may be omitted; keep existing content.
When images, logos or files are involved, read [attachments](references/attachments.md).
For a ChatGPT attachment, import its real file reference with import_client_file
and wait for READY; other clients can use the direct upload or app storage flow.
Use list_assets to identify READY owned uploads, then pass attachments with their
purpose and exact directions. To repeat a logo across pages, list all those pages
in the edit and reuse the exact asset; do not regenerate or crop it.
When the user requests a visual improvement, use plan-rabitmoon-visuals to choose
appropriate charts, icons, Mermaid or custom SVG. Describe the changed visual's
purpose, placement and styling in page instructions while preserving supplied
facts and the existing theme. A factual correction alone does not authorize
redesigning unrelated visuals or adding image generation.

A revision conflict requires a fresh read and reconciliation with the user's
intent before resubmitting; do not overwrite concurrent edits blindly. A retry of
the same accepted payload keeps the same idempotency key. Poll the existing job
at poll_after_seconds instead of starting another edit. Return status_url
immediately as "Open in editor": it opens the existing document with progress
and live updates. The owner may leave and reopen it; closing the browser does
not cancel the job. Editing resumes after the saved revision is loaded.

Return the owner-only URL and actual credits on completion. For failed/cancelled
work, report the reason, credit status and any draft URL. Pending billing is not
zero cost. Do not repeat a paid edit automatically. Cancel only when requested
and explain that already consumed work can still be charged.
