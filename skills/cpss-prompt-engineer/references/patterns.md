# Context-Specific Prompt Patterns

Load only the sections that match the target prompt. These are control patterns, not mandatory templates.

## ChatGPT Project instructions

Use when the prompt will persist as Project-level instructions rather than a single user message.

- Define the Project's purpose and governing behavior separately from task-specific requests.
- Specify precedence only where competing sources can plausibly conflict, such as user instructions, Project files, prior chats, memory, connected data, or external sources.
- Do not assume memory, connectors, tools, files, or cross-chat access beyond what the target environment actually provides.
- If correct behavior depends on mutable state across conversations, define the authoritative source and how conflicts or stale state are handled.
- Avoid embedding one-off task details into persistent instructions unless they are genuinely Project-wide invariants.
- Treat 8,000 characters, including spaces and line breaks, as the hard limit for the finished Project instruction artifact. Target 7,500 characters or fewer when practical to preserve revision headroom. Do not weaken required control merely to hit the target; compress lower-value wording first and never knowingly exceed the hard limit.
- Compress repeated warnings and duplicated rules; persistent instructions impose context cost on every turn.

## Research and analytical prompts

Use when factual reliability, current information, comparison, recommendations, or evidentiary reasoning materially affect the result.

- Define what requires verification and when current research is necessary rather than demanding browsing for every statement.
- Prefer primary or authoritative sources for material factual/capability claims; add secondary sources when comparison, interpretation, or independent confirmation is useful.
- Distinguish user-provided facts, verified facts, assumptions, inference, uncertainty, and recommendations when confusing them would change the conclusion.
- Require contradictions in material evidence to be surfaced and resolved or qualified rather than silently averaged away.
- Make research depth proportional to decision consequence and uncertainty. Stop when more research is unlikely to materially change the answer.
- For recommendations, define decision criteria and tradeoffs; do not convert popularity or plausibility into evidence.
- If a claim is unverifiable, require qualification rather than fabrication.

## Tool use and external actions

Use when the resulting prompt may read/write external systems, send messages, modify files, make bookings, schedule events, spend money, publish content, or cause other side effects.

- Define the intended action boundary and what requires confirmation or authorization.
- Do not invent tool availability, names, parameters, permissions, connected accounts, or successful execution.
- Separate read-only investigation from state-changing actions when the distinction matters.
- Require verification of important writes or side effects before claiming completion.
- Make irreversible, destructive, financial, privacy-sensitive, or broad-scope actions more conservative than reversible local actions.
- If the environment cannot perform the requested action, require a transparent limitation rather than pretending completion.

## High-stakes prompts

Use when errors could materially affect legal, financial, health, security, safety, compliance, irreversible decisions, or decisions explicitly intended to be acted on without review.

- Make the escalation visible to the user.
- Increase source quality and verification depth.
- Surface material uncertainty, assumptions, evidence gaps, and conflicts explicitly.
- Do not use confident wording beyond the evidence.
- Perform at least two validation passes for the finished instruction system.
- Do not replace missing material facts with silent assumptions.
- Preserve useful caveats without drowning the actual answer in generic disclaimers.

## Repeated or production workflows

Use when the prompt will be reused frequently or its consistency matters more than one successful run.

- Define observable success criteria and known failure modes.
- Prefer the smallest change targeted at demonstrated failures instead of wholesale rewriting.
- If representative examples or prior outputs are available, treat them as stronger optimization evidence than generic style heuristics.
- Keep examples diverse enough to cover meaningful edge cases and fully consistent with the written rules.
- Recommend testing the prompt on representative inputs when the user is making a durable workflow; do not claim an optimized prompt is universally better without evaluation evidence.
- When model/platform behavior is a dependency, design for re-validation rather than permanence.

## Strict output or classification tasks

Use when exact shape, labels, schema, formatting, or machine consumption matters.

- Specify only the fields, labels, order, syntax, or exclusions that are actually required.
- Define ambiguous classification boundaries directly; use examples if boundaries remain hard to express.
- Do not rely on prose conventions when a native structured-output mechanism is available and the target environment explicitly supports it.
- Keep examples valid under the same schema and rules as the desired output.

## Creative and open-ended prompts

Use when exploration, ideation, writing, or stylistic range is the goal.

- Do not add evidence, verification, rigid workflow, or exhaustive formatting rules unless requested or fact-dependent content makes them necessary.
- Specify audience, purpose, voice, constraints, and exclusions only to the extent they materially shape the result.
- Preserve creative latitude instead of turning taste preferences into a compliance checklist.
