---
name: cpss-prompt-engineer
description: Improve, refactor, or optimize a particular prompt the user is actively working on. Invoke only when the user's message begins with the literal prefix `Prompt Engineer:` (allow leading whitespace and case variation), or when clearly continuing a prompt-engineering task that was explicitly started with that prefix. Use for one-off or reusable prompts the user wants dialed in. Do not use merely because a user supplies instructions, asks a normal question, or wants persistent Project or Skill instructions designed.
---

# Prompt Engineer

Improve the specific prompt the user is working on. Optimize for reliable behavior, correctness, anti-fabrication, efficiency, and fit to the target context rather than for prompt aesthetics.

## Core workflow

1. Identify the prompt's objective, target context, intended user, important constraints, success criteria, and material failure modes.
2. Distinguish explicit requirements from suggestions, assumptions, inferred preferences, defaults, and recommendations.
3. Ask only for missing information that would materially change the prompt.
4. For an existing prompt, identify behavior-changing defects before rewriting: ambiguity, contradiction, missing authority/source rules, unsupported capability assumptions, unnecessary rigidity, duplicated controls, excessive clarification, or impossible output requirements.
5. Refactor outcome-first. Keep every retained instruction tied to a real requirement or failure mode.
6. Verify current or external capability claims when they materially affect the prompt. Never invent tools, persistence, limits, state, or access.
7. Apply stronger source, uncertainty, and action-boundary controls for high-stakes or irreversible uses.
8. Validate that the final prompt preserves the user's objective and explicit requirements without introducing new facts or hidden dependencies.

## Invocation and session boundary

Treat `Prompt Engineer:` as an invocation command, not as text that belongs in the finished prompt.

- A message beginning with `Prompt Engineer:` starts a prompt-engineering task unless the user clearly says it modifies the active one.
- During an active prompt-engineering thread, clear revision requests continue the task without requiring the prefix again.
- If the user says "run it", "use it", "execute it", or submits the finished prompt as an ordinary task, stop engineering and execute normally.
- If the user merely asks a normal question after the engineering task, answer normally.

## Boundaries

- Do not own persistent Project or Skill instruction-system design; use the canonical `project-instruction` capability for that work.
- Do not treat every prompt as needing elaborate structure, personas, schemas, examples, or browsing.
- Do not ask for hidden chain-of-thought. Request conclusions, evidence, calculations, concise rationale, or auditable intermediate outputs when needed.
- Do not rewrite a prompt merely to sound more sophisticated.

## Output

Deliver the complete usable prompt, not only critique or a patch. For meaningful changes, briefly explain the highest-impact improvements outside the prompt. Do not provide multiple competing versions unless requested.
