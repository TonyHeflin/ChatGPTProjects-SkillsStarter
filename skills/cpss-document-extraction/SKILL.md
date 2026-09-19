---
name: cpss-document-extraction
description: Extract and validate structured information from screenshots, PDFs, spreadsheets, pasted tables, scanned documents, forms, receipts, invoices, reports, or typed source text before downstream analysis or action. Use when document-reading accuracy matters and the task depends on correctly identifying fields, labels, figures, dates, names, statuses, totals, or table alignment. Separate confirmed values from ambiguity, flag unreadable or conflicting source content, and proceed only when required inputs are clear enough.
---

# Document Extraction

Extract only what the source supports, preserve context that affects meaning, and make ambiguity visible before downstream work.

## Required outcome

Before relying on the source:

1. State the important values or fields read from it.
2. Preserve labels, units, row/column relationships, and context when they affect meaning.
3. Distinguish confirmed information from assumptions or uncertain reads.
4. Flag missing, cropped, blurry, conflicting, misaligned, or unreadable content.
5. Continue downstream only when the required inputs are clear enough.

## Workflow

1. Inspect the source carefully before summarizing or calculating.
2. Identify the document type and extraction goal.
3. Read only content actually supported by the source.
4. Preserve exact wording when labels, categories, status text, units, or signs matter.
5. Organize extracted information to match the downstream task: named fields, rows/columns, totals, dates, entities, or statuses.
6. Check source-quality issues: cropped text, blurry scans, cut-off columns, row/column misalignment, conflicting repeated values, unclear units, or partially hidden content.
7. Validate visible totals/subtotals, headers, units, and alignment when relevant.
8. If required information remains unclear, present the confirmed extraction and ask only for the smallest missing clarification.

## Rules

- Do not invent values, labels, dates, totals, units, or entities.
- Do not silently normalize ambiguous content.
- Keep numbers, currency symbols, percentages, negative signs, and date formats accurate.
- Preserve table alignment.
- If a value has more than one plausible reading, say so.
- If repeated fields conflict, identify the conflict rather than choosing silently.

## Output

When useful, show a concise structured extraction before the downstream result. If the source is not clear enough, use:

- Confirmed extraction
- Needs confirmation
- Next step
