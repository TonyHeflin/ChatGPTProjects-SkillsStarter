---
name: cpss-prompt-project-reviewer
description: "Audit ChatGPT Project instructions, prompt systems, and their interaction with installed skills for conflicts, duplication, stale controls, trigger overlap, authority ambiguity, unnecessary complexity, missing routing, or instruction-limit pressure. Use automatically when the user asks to review, audit, check, simplify, validate, or reassess Project instructions or prompt architecture, asks what is missing or stale in a Project prompt, or wants a regression-style review after adding or changing skills. Do not use for general domain content review or whole-project workflow architecture when instructions are only one component."
---

# Prompt / Project Reviewer

Independently audit an existing prompt or ChatGPT Project instruction system. Review first; do not silently rewrite unless the user asks for changes.

## Scope

Focus on instruction behavior, not the underlying domain content unless domain facts are necessary to judge the instructions.

Audit:
- objective and role clarity;
- authority and precedence;
- Project-vs-skill responsibility split;
- skill routing and trigger coverage;
- conflicting or duplicated controls;
- stale assumptions about tools, files, memory, persistence, or platform behavior;
- controls that are ceremonial rather than behavior-changing;
- missing uncertainty, source, verification, or handoff rules where material;
- over-clarification or needless stopping;
- instruction growth and avoidable character pressure;
- contradictions between instructions, skill descriptions, examples, and expected workflows.

## Review method

1. Reconstruct what the Project is trying to accomplish and which components are meant to own which behaviors.
2. Distinguish Project invariants/context from reusable skill methodology.
3. Map important instructions to their behavioral purpose or failure mode.
4. Identify overlaps, conflicts, gaps, stale controls, and trigger problems.
5. Check whether source/tool/state assumptions are actually established.
6. Check whether any rule belongs in a skill, reference file, source document, or nowhere.
7. Check applicable Project instruction length limits when the user provides or the environment establishes one.
8. Reassess the whole system after findings; do not let local cleanliness hide architectural conflict.

## Architecture boundary

If the real question is broader than prompts/instructions and materially involves workflow ownership, persistent state, files, lifecycle, tools, cross-skill handoffs, or deciding where capabilities belong, route conceptually to `cpss-architecture-governance` rather than pretending this narrower review is sufficient.

This reviewer owns detailed instruction-quality findings; Architecture Governance owns ecosystem-level placement and ownership decisions.

## Findings

Classify issues when useful as:
- Conflict
- Duplication
- Missing control
- Stale assumption
- Routing/trigger gap
- Authority ambiguity
- Misplaced responsibility
- Unnecessary complexity
- Limit pressure
- No issue

Use severity only when it helps prioritize:
- Major — likely to cause materially wrong or inconsistent behavior.
- Moderate — meaningful reliability or maintenance problem.
- Minor — cleanup with limited behavioral impact.

For each material finding, state:
`instruction/component -> problem -> behavioral consequence -> recommended disposition`

Recommended dispositions may be: keep, delete, merge, move to Project, move to skill, move to reference/source, or clarify.

## Output

Lead substantial reviews with a BLUF stating whether the instruction system is coherent and the strongest issues.

Then provide the highest-impact findings, missing context that limits the review, and what should remain unchanged.

Do not rewrite the full prompt unless the user asks. When the user asks to implement justified changes to durable Project or Skill instructions, hand them to the canonical `project-instruction` capability. Use `cpss-prompt-engineer` only for a particular prompt under its explicit invocation rules.

## Guardrails

Do not invent installed skills, tool capabilities, memory behavior, source precedence, or platform guarantees.
Do not recommend moving a rule merely to make the prompt shorter; move it only when ownership is better elsewhere.
Do not treat stylistic preference as an architectural defect.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://prompt-project-reviewer/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
