# Architecture

## Core model

**Projects are domain workspaces. Skills are reusable capabilities.**

A Project owns persistent context for a subject or body of work: purpose, domain-specific rules, important files/references, and enduring constraints.

A Skill owns a reusable method, workflow, convention, or specialized behavior that may be useful across multiple Projects.

Ordinary one-off task details belong in the conversation rather than persistent instructions.

## Canonical foundational Projects

### General Analysis / Research

A broadly useful domain workspace for evidence-sensitive analysis, research, explanation, comparison, and evaluation.

### Project Instruction

The canonical workspace for designing and maintaining durable Project and Skill instructions.

`Project Instruction` remains unprefixed. It is not branded as a CPSS-specific domain because its role is architectural and canonical within the environment.

## Skill provenance and namespacing

The starter's custom infrastructure Skills use `cpss-` internal names where appropriate. This serves two purposes:

1. Make starter provenance visible.
2. Reduce direct name collisions in existing accounts.

Human-facing display names remain clean and descriptive.

The dedicated `project-instruction` Skill remains unprefixed to match the canonical Project Instruction role.

Namespacing is not a substitute for collision analysis. Two differently named Skills can still compete for the same user request if their trigger descriptions overlap.

## Non-destructive existing-account policy

The bootstrap does not assume the account is empty.

Before creating anything, it performs a **quick collision preflight** against only the components it intends to create.

It does not perform a general cleanup, rewrite the user's architecture, or decide what the user "should" have.

Existing Projects, Skills, instructions, files, and settings are preserved.

## Substitution standard

An existing component does not satisfy a starter requirement merely because it has a similar name or purpose.

Substitution requires inspection of the actual instructions/behavior and evidence that the existing component provides **equal or greater rigor** for the required role.

If equivalence cannot be established, it is unproven and the component must not silently replace the starter definition.

The comparison should consider responsibilities, boundaries, trigger precision, material controls, platform assumptions, dependencies, source/freshness/uncertainty rigor where applicable, and the effect on ownership/routing elsewhere in the environment.

## Progressive Interview

Progressive Interview is standalone interaction behavior, not an orchestration stage.

Its purpose is to prevent large questionnaire dumps. It activates only when a response would otherwise need many dependent clarifying questions, asks progressively, and then gets out of the way so the original task can continue.

## Environment Help

Environment Help is the plain-language customization front door. It should let a user describe a goal without already knowing whether the solution is a Project, Skill, instruction change, connector, or something else.

It explains and routes. It does not silently redesign the architecture.

## User-mediated actions

Whenever setup requires user action, ChatGPT must explain:

- what has already been prepared;
- exactly what the user must do;
- where to click;
- what result to expect;
- whether the action navigates away from the bootstrap conversation;
- how to return and continue.

If navigation would leave the bootstrap chat, the user should be told to use a **new browser tab** and keep the bootstrap tab open.

## Documentation

Markdown files in the repository are canonical.

Generated DOCX, PDF, archive, or other renderings may be produced when specifically useful, but they are not maintained as parallel authoritative copies.
