---
name: cpss-research
description: "Conduct source-grounded research that turns an idea, question, or premise into a concise, decision-useful evidence base while preserving a complete downstream handoff. Use when the user asks to research an idea, topic, option set, market, policy, product, organization, technical question, or current issue; compare alternatives; map a landscape; gather evidence; or build a premise from research. Default to a concise summary, offer deeper detail on request, and create a self-contained numbered Markdown research checkpoint for substantive completed runs when file creation is available."
---

# Research

Research broadly enough to answer the user's actual question, but stop when additional work is unlikely to materially change the answer, major contradictions have been surfaced, and important uncertainties are known.

## Workflow

1. Define the research question and scope.
   - Preserve the user's objective, constraints, decision context, and stated assumptions.
   - Ask only when a missing fact would materially change the research direction. Otherwise proceed with a clearly bounded interpretation.

2. Gather evidence.
   - Use current external research whenever the subject is time-sensitive, niche, disputed, recommendation-sensitive, or otherwise not reliably answerable from stable knowledge alone.
   - Prefer primary, official, original, or otherwise authoritative sources for material factual claims.
   - Use strong secondary sources for context, comparison, interpretation, discovery, and independent corroboration.
   - Follow important claims back toward their original evidence when practical rather than relying on repeated summaries.

3. Build the evidence base.
   - Separate verified facts, user-provided facts, assumptions, inferences, uncertainties, and recommendations when confusing them would change the conclusion.
   - Record the scope, timeframe, population, geography, definitions, units, and comparison baseline when material.
   - Surface credible contradictory evidence rather than smoothing it away.
   - Note important source limitations, inaccessible evidence, or freshness concerns.

4. Synthesize.
   - Answer the research question directly.
   - Explain what the evidence supports, what remains uncertain, and what appears to matter most.
   - For comparisons or recommendations, state the meaningful decision criteria and tradeoffs.
   - Do not convert popularity, plausibility, or repeated citation into proof.

5. Stop at practical sufficiency.
   - Stop when further searching is unlikely to materially change the answer, the important evidence categories are represented, material contradictions are surfaced, and remaining gaps are explicit.
   - Continue deeper only when consequence, uncertainty, or the user's request justifies it.

## Output depth

Default to a concise summary that contains:
- the bottom line;
- the most important findings;
- material uncertainty or disagreement;
- minimal inline source provenance/citations;
- a short note that standard or full detail is available on request.

If the user requests `standard`, provide enough evidence and reasoning to evaluate the conclusion without reproducing the entire working record.

If the user requests `full`, provide a complete research report with source discussion, evidence, contradictions, assumptions, uncertainties, and supporting detail.

Visible output depth must never reduce the completeness of the downstream working record.

## Research checkpoint and handoff

For every substantive completed research run, maintain a complete self-contained research record using `references/handoff.md`.

When the environment supports file creation, create a Markdown checkpoint named:
- `research-record-01.md`
- `research-record-02.md`
- and so on for later passes in the same research thread.

Each new checkpoint must contain the complete current state, not only differences from the previous version. Treat the latest checkpoint as the default handoff to a later validation step. Earlier checkpoints are history, not competing current state.

If file creation is unavailable, preserve the same structured record in the conversation and state that no file was created.

Do not automatically invoke another skill or advance the workflow. If the user later asks to validate the research, the latest complete record should be sufficient input for a research-validation pass.

## Finalization and cleanup

When the user says "lock it in", "finalize this", "this is good", or equivalent:
- treat the latest checkpoint as canonical;
- remove older checkpoint files from the same series only when deletion is available and clearly safe;
- never delete source documents, unrelated artifacts, or evidence files;
- if deletion is unavailable or provenance should be preserved, keep the older files but mark the latest record as canonical.

## Boundaries

- Do not fabricate sources, access, findings, dates, quotes, measurements, or current status.
- Do not hide evidence gaps to make the answer smoother.
- Do not force exhaustive research when the answer is already decision-sufficient.
- Do not perform a formal claim-validation audit unless the user asks for validation or the active task explicitly requires it.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://research/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
references/handoff.md
