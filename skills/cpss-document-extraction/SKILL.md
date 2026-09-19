---
name: cpss-document-extraction
description: "extract and validate structured information from screenshots, PDFs, spreadsheets, pasted tables, scanned documents, or typed source text before downstream analysis, classification, summarization, or action. use when document reading accuracy matters more than speed."
---

# Document Extraction

## Overview

Use this skill when a task depends on accurately reading information from a source document before doing downstream work.

Typical inputs include screenshots, PDFs, spreadsheets, pasted tables, scanned forms, receipts, invoices, reports, or typed document text.

Your job is to extract only what the source supports, organize it clearly, and separate confirmed values from assumptions or unresolved ambiguities.

## Use This Skill For

Use this skill when the request involves any of the following:

- extracting fields, figures, labels, dates, names, statuses, or totals from a document
- verifying whether information was read correctly from a screenshot or PDF
- turning semi-structured document content into clean inputs for a downstream workflow
- identifying unreadable, cropped, ambiguous, or inconsistent source content before analysis

Do not use this skill when the source content is already confirmed and the main task is interpretation rather than extraction.

## Required Outcome

Before downstream work, produce an extraction that:

1. states the important values or fields read from the source
2. preserves labels or context when they affect meaning
3. distinguishes confirmed information from assumptions
4. flags missing, ambiguous, conflicting, or unreadable content
5. proceeds only when the required source inputs are clear enough

## Workflow

1. Inspect the source carefully before summarizing or calculating.
2. Identify the document type and the extraction goal.
   - Examples: invoice, receipt, form, table, spreadsheet, statement, report, application, schedule.
3. Read only content that is actually supported by the source.
4. Preserve exact wording when labels, categories, or status text matter.
5. Organize extracted information into a structure that matches the task.
   - Examples: named fields, rows and columns, totals, dates, entities, status values.
6. Check for source-quality issues that may reduce reliability.
   - cropped text
   - blurry scans
   - cut-off columns
   - row/column misalignment
   - conflicting repeated values
   - unclear units or labels
7. If the required information is clear enough, continue with the downstream task.
8. If required information is unclear, stop and provide an extraction summary first, then ask only for the smallest clarification needed.

## Extraction Rules

- Do not invent values, labels, dates, totals, units, or entities.
- Do not silently normalize ambiguous source content.
- Keep numbers, currency symbols, percentages, negative signs, and date formats accurate.
- Preserve row-to-column alignment when reading tables.
- If a value has more than one plausible reading, say so explicitly.
- If the same field appears more than once with conflicting values, identify the conflict instead of choosing silently.
- If a downstream task depends on a specific field name, make sure the extracted value is tied to the correct label.

## Validation Checks

Before relying on the extraction, check:

- whether visible totals or subtotals reconcile when that matters
- whether headers match the values beneath them
- whether units appear consistent across the source
- whether the requested fields are all present
- whether any values seem shifted into the wrong row or column
- whether the source contains cropped, blurry, or partially hidden text that affects the result

If a validation check fails, say exactly what failed and what can still be used safely.

## Output Contract

When the source is clear enough, present a concise structured extraction before or alongside the downstream result when that improves reliability.

When the source is not clear enough, present:

### Confirmed extraction
- list the values or fields you could read confidently

### Needs confirmation
- list only the unclear, missing, or conflicting items

### Next step
- ask for the smallest missing clarification needed to continue

Use precise wording such as:
- "I read the invoice total as $1,482.00."
- "The due date appears to be 2026-05-15."
- "The vendor name is partially cropped, so I cannot confirm it confidently."

## Request Patterns

### Pattern 1: Screenshot or PDF to structured fields

Goal: extract the fields needed for a downstream task.

Expected result:
- a clean field list or table
- ambiguity called out explicitly
- downstream work only if required fields are clear

### Pattern 2: Verify a prior extraction

Goal: confirm whether previously read values match the source.

Expected result:
- compare claimed values against the document
- identify mismatches precisely
- separate confirmed, corrected, and unclear items

### Pattern 3: Spreadsheet or pasted table to normalized inputs

Goal: convert semi-structured tabular data into clearly named inputs.

Expected result:
- field names mapped to source values
- alignment and units checked
- ambiguity flagged before downstream analysis

## Reliability Priorities

Optimize for extraction accuracy over speed or polish.

A short clarification question is better than a confident downstream answer built on an uncertain read.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://document-extraction/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
