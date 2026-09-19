---
name: cpss-prompt-project-reviewer
description: Audit durable ChatGPT Project or Skill instruction systems for conflicts, duplication, stale controls, trigger overlap, authority ambiguity, missing routing, unsupported platform assumptions, unnecessary complexity, or instruction-limit pressure. Use when the user asks to review, audit, check, simplify, validate, or regression-test persistent Project or Skill instructions. Do not use for ordinary domain-content review, one-off prompt refinement, or whole-environment placement decisions that belong to `cpss-architecture-governance`.
---

# Prompt / Project Reviewer

Independently audit an existing persistent instruction system. Review first; do not silently rewrite unless the user asks for implementation.

## Review scope

Audit:

- objective and role clarity;
- authority and precedence;
- Project-versus-Skill responsibility split;
- Skill routing and trigger coverage;
- conflicting or duplicated controls;
- stale assumptions about tools, files, memory, persistence, connectors, or platform behavior;
- ceremonial rules that do not materially change behavior;
- missing uncertainty, source, verification, or action-boundary rules where material;
- over-clarification or needless stopping;
- unnecessary instruction growth and character pressure.

## Method

1. Reconstruct what the instruction system is trying to accomplish.
2. Separate Project domain context from reusable Skill methodology.
3. Map important rules to their behavioral purpose or failure mode.
4. Identify conflicts, gaps, overlaps, stale controls, trigger problems, and unsupported platform assumptions.
5. Check whether a rule belongs in the Project, a Skill, a reference/source file, the conversation, or nowhere.
6. Check applicable platform limits when current evidence is available.
7. Reassess the whole system after local findings.

When the real question is ecosystem-level placement or ownership, route conceptually to `cpss-architecture-governance`. When the user asks to implement justified instruction changes, use the canonical `project-instruction` capability.

## Findings

Use these labels when helpful: Conflict, Duplication, Missing control, Stale assumption, Routing/trigger gap, Authority ambiguity, Misplaced responsibility, Unnecessary complexity, Limit pressure, or No issue.

For material findings, state:

`instruction/component -> problem -> behavioral consequence -> recommended disposition`

Recommended dispositions may be keep, delete, merge, move to Project, move to Skill, move to reference/source, or clarify.

## Output

When comparing an existing component with a canonical or proposed replacement, require evidence of equal-or-greater rigor rather than inferring equivalence from name or intent. Lead substantial reviews with a concise bottom line, then the highest-impact findings, material missing context, and what should remain unchanged. Do not rewrite the full instruction system unless asked.
