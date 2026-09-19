---
name: cpss-progressive-interview
description: "Guide lightweight, adaptive requirements discovery when a request is materially underdefined and several unknowns interact, especially when later questions depend on earlier answers. Use for creating Projects, Skills, workflows, plans, configurations, specifications, or other work where ChatGPT would otherwise ask a long questionnaire. Ask one high-value question at a time by default, adapt the next question to the answer, use reasonable defaults for low-impact details, and stop once enough information exists to proceed reliably. Do not invoke for a single obvious clarification or when the user has already supplied sufficient requirements."
---

# Progressive Interview

Run requirements discovery as a decision tree, not a questionnaire.

## Core rules

1. Ask the smallest high-value question first.
2. Ask one primary question at a time by default. Ask two only when they are tightly coupled and naturally answered together.
3. Never ask a question now if its relevance or wording depends materially on an unanswered earlier question.
4. After every answer, update the working model and choose the next question from the remaining uncertainty.
5. Prefer reasonable, reversible defaults for low-impact details. State important defaults when they affect the result; do not interrogate the user about minutiae.
6. Stop interviewing as soon as enough information exists to proceed reliably. Do not seek a perfect specification.
7. Use information already supplied in the conversation. Never re-ask an answered question.
8. If the user appears to want momentum more than precision, make bounded assumptions and proceed unless a missing fact could materially change the objective, architecture, safety, or result.

## Question priority

Classify unresolved information internally before asking:

- **Required now** — could materially change the objective, architecture, scope, safety, or ability to proceed. Ask when needed.
- **Branching** — determines which later questions are relevant. Ask early.
- **Useful later** — helpful but not needed for the current decision. Defer.
- **Defaultable** — choose a sensible reversible default and mention it if material.
- **Minutiae** — omit unless the user specifically cares or later evidence makes it important.

Prefer questions that eliminate the largest number of downstream possibilities.

## Interview loop

Repeat only while material uncertainty remains:

1. Summarize the current understanding internally.
2. Identify the single unresolved fact with the highest branching or decision value.
3. Ask it plainly, without presenting the rest of the hidden question list.
4. Incorporate the answer.
5. Remove questions that are now irrelevant or safely defaultable.
6. Stop and proceed when the task is sufficiently specified.

Do not announce every iteration or expose an internal checklist unless the user asks to see it.

## Starting broad

Begin with purpose and outcome before implementation details.

Good opening questions often ask one of:

- What are you trying to accomplish?
- Who will use this?
- What would make this successful?
- Is this ongoing work that needs persistent context, or a one-off task?
- Which constraint matters most here?

Choose only the question that best separates the likely paths.

## Project creation pattern

When helping create a ChatGPT Project, discover only enough to establish a useful first version. A typical progression may be:

1. Ask what area of work or life the Project should support.
2. Based on that answer, determine whether the work needs persistent domain context, recurring workflows, authoritative files, special tone/behavior, or external tools.
3. Ask only the next material branch question.
4. Once purpose, authoritative context, important constraints, and recurring behavior are clear enough, hand the result to the appropriate Project/prompt construction method.
5. Leave cosmetic formatting and speculative future workflows for later iteration.

Do not dump a standard Project questionnaire on the user.

## Skill and workflow creation pattern

For a new Skill or workflow, establish in this order only as needed:

1. Representative use case or desired outcome.
2. Expected input.
3. Expected output.
4. Tool/connector dependency only if relevant.
5. Important failure or boundary conditions.

If an early answer makes later items obvious or irrelevant, do not ask them separately.

## Handoff

When the interview has enough information:

- state the resulting understanding briefly;
- identify any material assumption that remains;
- pass the clarified requirements to the task-specific capability, such as `prompt-engineer`, `skill-creator`, or `architecture-governance` when available;
- continue the actual task rather than ending with an unnecessary confirmation question.

## Boundaries

Do not use this skill merely because a request is short. Many short requests are sufficiently clear.

Do not use it to delay work that can proceed safely with a reasonable assumption.

Do not turn preference discovery into an exhaustive survey.

Do not ask the user to choose among implementation details they do not need to care about when ChatGPT can select a safe, reversible default.

Do not replace domain-specific safety or required intake procedures. If another applicable workflow requires specific information, gather that information progressively rather than dumping the full form unless simultaneous collection is genuinely necessary.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://progressive-interview/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
