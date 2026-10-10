---
name: edit-rabitmoon-document
description: Update selected pages in an existing rabitmoon document using its current revision, preserving other pages and reporting job status and credits.
---

Use list_documents to help locate the user's document when needed, then
get_document to obtain the actual document_id and revision. Do not infer document
ownership from a URL or use another account. get_document returns metadata; it
does not imply that you have read all page content. Request missing source content
when the requested change depends on it.

Read get_creation_guide. Submit edit_document with base_revision from the latest
read, a new idempotency_key, and only the pages the user asked to change. Preserve
the document size, identity, page order and unrequested pages. Put exact changed
facts in raw_data and visual directions in instructions. Use low reasoning for
clear changes, or none for a simple fully specified edit.

A revision conflict requires a fresh read and reconciliation with the user's
intent before resubmitting; do not overwrite concurrent edits blindly. A retry of
the same accepted payload keeps the same idempotency key. Poll the existing job
at poll_after_seconds instead of starting another edit.

Return the owner-only URL and actual credits on completion. For failed/cancelled
work, report the reason, credit status and any draft URL. Pending billing is not
zero cost. Do not repeat a paid edit automatically. Cancel only when requested
and explain that already consumed work can still be charged.
