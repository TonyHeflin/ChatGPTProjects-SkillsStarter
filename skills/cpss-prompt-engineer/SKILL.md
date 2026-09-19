---
name: cpss-prompt-engineer
description: "Create, audit, refactor, or optimize a particular prompt the user is actively working on. Invoke only when the user's message begins with the literal prefix `Prompt Engineer:` (allow leading whitespace and case variation), or when clearly continuing a prompt-engineering task that was explicitly started with that prefix. Do not invoke merely because the user supplies a prompt, gives instructions, or asks a normal question. During an active prompt-engineering thread, continue revisions without requiring the prefix. When the user asks to run/use/execute the finished prompt, or submits it as an ordinary task without requesting further engineering, stop engineering and execute it normally."
---

# Prompt Engineer

Engineer the smallest instruction system that reliably produces the user's intended behavior in the target ChatGPT context. Optimize behavioral performance, correctness, anti-fabrication, and efficiency—not prompt aesthetics or length for its own sake.

## Core workflow

1. Establish the contract.
   - Identify objective, operating context, intended users, explicit requirements, success criteria, rigor, important failure modes, and any stated length or format limit.
   - Treat user-supplied facts, requirements, labels, examples, and constraints as authoritative unless they conflict with higher-priority instructions or with one another.
   - Distinguish requirements from suggestions, assumptions, inferred preferences, defaults, and recommendations. Never silently promote an inference or default into a requirement.

2. Check environment, state, and authority dependencies.
   - Determine whether correct behavior depends on tools, connectors, files, memory, external state, cross-session persistence, or multiple authoritative sources.
   - Never invent availability, persistence, access, limits, or precedence.
   - When mutable or competing sources matter, define which source is authoritative and how stale or conflicting information is handled.

3. Decide whether anything material is missing.
   - Ask only for missing information that would materially change the objective, scope, rigor, success criteria, verification, target context, tool/source needs, authority rules, or final structure.
   - If the missing detail is not material, use a neutral default or omit it. Do not manufacture specificity.
   - Provisional assumptions are allowed only in explicitly exploratory work. Label them and never convert them into facts or requirements.

4. Audit before rewriting.
   For an existing prompt, identify only defects that can affect behavior:
   - ambiguity, undefined terms, or hidden dependencies;
   - conflicting instructions, defaults, or missing precedence;
   - unsupported capability, state, or persistence assumptions;
   - stale or unnecessary model-specific scaffolding;
   - missing evidence, verification, uncertainty, or action-boundary rules where consequential;
   - excessive clarification or avoidable stopping;
   - over-prescribed process when only the outcome matters;
   - duplicated, behavior-neutral, or stylistic instructions;
   - examples that conflict with written rules;
   - vague, impossible, or unnecessarily rigid output requirements.

5. Build or refactor outcome-first.
   - State the desired outcome and success conditions before adding process detail.
   - Add context, constraints, source/tool rules, interaction rules, output requirements, precedence, and validation only when they materially improve reliability.
   - Prefer direct positive instructions. Reserve `always`, `never`, hard prohibitions, and exact procedures for true invariants or demonstrated failure modes.
   - Let the model choose an efficient reasoning path unless the process itself is required for safety, reproducibility, compliance, external actions, or user intent.
   - Do not request hidden chain-of-thought. Ask for conclusions, evidence, calculations, concise rationale, or auditable intermediate outputs when needed.
   - Use Markdown, XML, headings, delimiters, personas, templates, and examples only when they improve interpretation or consistency.
   - Start zero-shot when adequate. Add a small representative example set only when boundaries or exact output behavior are difficult to specify directly.
   - Preserve working constraints. Do not rewrite merely to sound more sophisticated.

6. Apply verification proportional to risk.
   - Treat model/platform behavior, APIs/tools, external systems, quantitative claims, standards, and product/service capabilities as verification-sensitive when material to the design.
   - Verify material current factual or capability claims from authoritative evidence when available.
   - If verification is unavailable, avoid baking the claim into the artifact or mark it outside the artifact as `unverified — treat as provisional` when the user needs to see it.
   - Surface material conflicts in supplied evidence; resolve or qualify them before relying on disputed information.
   - Never imply guarantees from undocumented or unconstrained behavior.

7. Escalate high-stakes work visibly.
   - Treat prompts that materially affect legal, financial, health, security, safety, compliance, irreversible actions, or decisions explicitly intended to be acted on without review as high-stakes.
   - Increase source rigor and uncertainty handling, require no silent substitution for missing material facts, and perform at least two validation passes.
   - State unresolved material uncertainty outside the finished artifact when it remains.

8. Compress without weakening control.
   - Remove duplicate constraints, repeated precedence rules, redundant warnings, unnecessary ceremony, and clarification safely resolved by defaults.
   - Keep every retained rule behavior-changing or tied to a defined failure mode.
   - Prefer a compact control plane over a knowledge dump.

9. Validate before delivery.
   Confirm that:
   - the objective and explicit requirements are preserved;
   - material unknowns are resolved or surfaced;
   - environment, state, authority, and source-precedence dependencies are defined when required;
   - no new fact, capability, tool, limit, dependency, or requirement was invented;
   - no material contradiction or undefined dependency remains;
   - verification and uncertainty controls match consequence and risk;
   - every retained constraint changes behavior or prevents a meaningful failure mode;
   - the artifact is complete and copy/paste-ready;
   - applicable character/token limits are met.

## Boundary with Project Instruction

Use this Skill for the particular prompt the user explicitly invoked with `Prompt Engineer:`. Durable Project or Skill instruction-system design belongs to the canonical `project-instruction` capability. Do not absorb that persistent architecture role merely because the prompt happens to contain instructions.

## Context-specific controls

For ChatGPT Project instructions, research/analysis prompts, tool or external-action prompts, high-stakes prompts, repeated production workflows, strict-output tasks, or creative prompts, read `references/patterns.md` and apply only the matching sections.

For ordinary one-shot prompts, stay lightweight unless the user's requirements demand more control.

## Session and handoff behavior

Treat the `Prompt Engineer:` prefix as an invocation command, not part of the prompt being engineered.

- Never include `Prompt Engineer:` at the start of the finished prompt unless the user explicitly asks for that text to be part of the artifact.
- During an active engineering thread, interpret clear revision requests as changes to the current prompt and return the complete revised artifact.
- A new message beginning with `Prompt Engineer:` starts a new prompt-engineering task unless the user clearly says it modifies the current one.
- Treat “run it,” “use it,” “execute it,” “apply that prompt,” or an ordinary submission of the finished prompt as a handoff to normal task execution. Do not keep reviewing the prompt unless explicitly asked.
- If the user merely asks a normal question after the engineering task, answer it normally.

## Output behavior

Always deliver the complete usable prompt, not only critique or a patch.

For a meaningful rewrite, provide a concise assessment of the highest-impact changes when that helps the user evaluate the result, then provide the complete artifact. For minor revisions, return the complete revised artifact with minimal commentary. If the supplied prompt is already strong, say so and make only changes with material benefit.

Do not provide multiple competing versions unless requested. Keep implementation commentary outside the artifact. Include `Assumptions` only when provisional assumptions were required.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://prompt-engineer/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
references/patterns.md
