---
name: cpss-research-validation
description: "Use when the user wants research outputs to be source-grounded, freshness-checked, claim-vetted, citation-backed, or clearly qualified before findings are presented. Especially useful for grant prospecting, nonprofit landscape scans, operational research, board memos, and any decision-grade briefing where unsupported or stale claims would create risk."
---

# Research Validation

## Overview

Use this skill whenever a research task needs disciplined verification before conclusions are presented. Treat this skill as a validation layer that sits between raw research and the final answer.

Your job is to prevent:
- unsourced factual claims
- stale deadlines or availability claims
- inferred eligibility presented as confirmed
- overconfident summaries built on thin evidence
- decision-ready outputs that hide uncertainty

Apply this skill especially when working on:
- grant prospecting
- regional nonprofit or partnership mapping
- operational or policy research
- board briefings
- comparison tables
- service gap or landscape summaries

## Core Validation Rules

1. Do not present a material claim as fact unless it is supported by a source.
2. Prefer primary or official sources over summaries, directories, or commentary.
3. For time-sensitive claims, verify current status before presenting them as active.
4. Separate confirmed facts from interpretation, inference, and open questions.
5. If evidence is thin, say so plainly instead of smoothing over the gap.
6. If a stronger source is unavailable, lower confidence rather than upgrading the claim.

## Source Hierarchy

Use this order of preference:
1. the organization's own official site for facts about that organization
2. official funder pages for grant facts
3. official nonprofit, government, agency, university, or institutional pages for factual claims
4. IRS, state, or other official public sources for compliance, tax, or regulatory matters
5. secondary sources only as supporting context and only when clearly labeled

Do not let a weaker source override a stronger source without explicitly noting the conflict.

## Validation Workflow

For each research task:

1. Break the work into material claims or decision-relevant fields.
2. Validate each material claim against the best available source.
3. Mark each claim or row as one of:
   - Verified
   - Partially verified
   - Unverified (provisional)
4. Check whether any claim is freshness-sensitive.
5. If freshness-sensitive, verify current status before presenting it as live, available, or active.
6. Remove or soften any unsupported conclusion.
7. Preserve open questions instead of filling them with guesswork.

Use this claim-by-claim mindset for:
- grant eligibility
- deadlines
- funding amounts
- restrictions
- region served
- services offered
- partnership fit
- service availability
- policy or compliance statements
- organizational comparisons

## Freshness Checks

Freshness checks are mandatory for:
- grants
- deadlines
- regulations
- service availability
- local organizations
- tax or compliance-related claims

When a freshness check is required:
- verify the claim on a current source before presenting it as active
- state when the information was checked if it materially helps the user judge risk
- if freshness cannot be confirmed, mark the claim as provisional

Never present stale grants or deadlines without a date check.
Never assume a local organization still operates the same services unless recent evidence supports it.

## Grant Validation Rules

For grant work, validate each opportunity against the official funder page before treating it as a real prospect.

At minimum, verify or explicitly flag uncertainty for:
- opportunity or funder name
- eligibility
- geographic fit
- programmatic fit
- deadline
- funding amount or range
- restrictions
- match requirement if stated
- application complexity if evidence supports it
- source links

If eligibility is not explicit, do not mark the grant as eligible. Say eligibility is unconfirmed.
If the deadline is not confirmed on a current source, say that clearly.
If a grant page is archived, old, ambiguous, or indirect, lower confidence immediately.

## Organizational and Landscape Validation Rules

For nonprofit scans, partner maps, and service landscapes, validate each organization entry separately.

At minimum, separate:
- confirmed mission
- region served
- services offered
- possible overlap
- possible partnership value
- open questions

Only the first three should be treated as factual fields, and only when sourced.
The latter three are analytical fields and must be framed as interpretation, not fact.

If an organization appears only in a directory, list, or news story and you cannot confirm details on an official site, mark the entry as partially verified or unverified.

## Confidence Labeling

Use these labels conservatively:

### Verified
Use when the relevant fact is supported by strong, current, primary or official sourcing.

### Partially verified
Use when some core elements are confirmed but an important field remains unconfirmed, outdated, indirect, or inferred.

### Unverified (provisional)
Use when evidence is thin, outdated, indirect, or not authoritative enough to support confident use.

Do not upgrade a claim just because it seems plausible.

## Output Contract

When this skill is active, the final output should do all of the following:
- keep citations or source links close to material claims
- distinguish facts from interpretation
- preserve open questions
- show uncertainty clearly when evidence is incomplete
- avoid turning thin evidence into strategic certainty

When the output is tabular, add confidence labels per row or per field group whenever practical.
When the output is memo-style, include a short section for risks, caveats, or open verification questions whenever uncertainty could affect a decision.

## Escalation Rules

Escalate uncertainty instead of forcing a conclusion when:
- primary evidence is missing
- multiple sources conflict materially
- freshness cannot be confirmed
- eligibility is implied but not stated
- a legal, tax, or compliance answer would require professional interpretation
- the user asks for certainty beyond what the evidence supports

In those cases:
- state the limit directly
- give the strongest qualified answer available
- identify the next best verification step

## Boundaries

Do not:
- present unsourced claims as fact
- present stale deadlines as current
- present inferred eligibility as confirmed
- overstate service availability or local landscape certainty
- provide legal or tax advice
- hide uncertainty just to make the output read more smoothly

## Example Triggers

- "Find current grants for Foster House and verify which ones are real prospects."
- "Map organizations in Huntsville that overlap with foster care and kinship support, but separate confirmed facts from assumptions."
- "Draft a board briefing on comparable nonprofit models and clearly label what is verified versus provisional."


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://research-validation/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
