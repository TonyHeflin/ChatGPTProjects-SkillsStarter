---
name: cpss-progressive-interview
description: Prevent overwhelming questionnaire dumps. Use when ChatGPT is about to ask the user a long or branching set of clarification, setup, intake, or requirements questions in one response, especially when answers to early questions would materially change which later questions matter. Ask one high-value question at a time by default, adapt after each answer, use reasonable defaults for low-impact details, and stop as soon as enough information exists to continue the original task. Do not invoke for a single clarification, a short naturally grouped set of questions, or merely because the task involves Projects, Skills, plans, or configuration.
---

# Progressive Interview

Turn a large questionnaire into a lightweight adaptive conversation, then return control to the original task.

## Core rules

1. Ask the smallest high-value question first.
2. Ask one primary question at a time by default. Ask two only when they are tightly coupled and naturally answered together.
3. Do not ask a question now if its relevance or wording depends materially on an unanswered earlier question.
4. After each answer, update what is known and choose the next question from the remaining material uncertainty.
5. Prefer sensible, reversible defaults for low-impact details. Mention a default only when it matters.
6. Stop questioning as soon as enough information exists to proceed reliably. Do not seek a perfect specification.
7. Never re-ask information already supplied.
8. If the task can proceed safely with a bounded assumption, proceed rather than extending the interview.

## Question priority

Treat unresolved information internally as:

- Required now: could materially change the objective, scope, architecture, safety, or result.
- Branching: determines which later questions are relevant.
- Useful later: helpful but not needed yet.
- Defaultable: safely choose a reversible default.
- Minutiae: omit unless the user specifically cares.

Prefer the question that removes the most downstream uncertainty.

## Stop and resume

When enough information is known:

- briefly state the resulting understanding only if useful;
- note any material remaining assumption;
- continue the original task normally.

Do not make Progressive Interview a required workflow stage, a handoff destination, or an architecture dependency. Its job is only to improve the interaction when the alternative would be an excessive questionnaire.
