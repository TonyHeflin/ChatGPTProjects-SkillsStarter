---
name: project-instruction
description: Design, revise, and maintain durable instructions for ChatGPT Projects and Skills. Use when the user wants to create or change persistent Project instructions, a Skill's behavioral instructions, responsibility boundaries between Projects and Skills, or an instruction system that should govern repeated work over time. Preserve domain context in Projects and reusable methods in Skills. Do not use for dialing in a one-off prompt; use `cpss-prompt-engineer` for that. Do not package or install Skills unless the user separately asks for Skill Creator to do so.
---

# Project Instruction

Create the smallest durable instruction system that reliably governs repeated work over time.

## Core model

- A Project is a domain workspace. Its instructions own persistent domain purpose, subject-specific rules, authoritative context, and enduring operating constraints.
- A Skill owns reusable methods, workflows, conventions, or specialized behavior that can apply across Projects.
- Reference files own durable facts, specifications, templates, canon, inventories, or source material that should be consulted rather than embedded into instructions.
- Ordinary task details belong in the conversation, not in persistent instructions.

## Workflow

1. Establish the durable behavior that must persist and the target component: Project instructions, Skill instructions, or both.
2. Preserve explicit user requirements and distinguish them from examples, preferences, assumptions, and recommendations.
3. Identify authoritative sources and precedence only where competing sources can realistically conflict.
4. Place domain-specific context in the Project and reusable methodology in Skills. Avoid copying full Skill methods into Project instructions.
5. Remove one-off task details, duplicated rules, stale platform assumptions, unsupported capability claims, and instructions that do not change behavior.
6. Keep the instruction set maintainable. Prefer direct rules over ceremonial process.
7. For Skill instructions, write clear trigger conditions in the description and keep the body focused on execution after the Skill has triggered.
8. For Project instructions, keep within the platform's current instruction limits when known; verify limits rather than assuming them when material.
9. When an existing Project or Skill may overlap, preserve it and compare its actual instructions/behavior before treating it as a substitute. Similar names or descriptions are not evidence of equivalence. Only substitute when equal-or-greater rigor is established for the required role; otherwise treat equivalence as unproven.
10. Validate the complete system for contradictions, missing ownership, trigger overlap, authority ambiguity, unsupported platform assumptions, and unnecessary context cost.

## Interaction with other capabilities

- Use `cpss-architecture-governance` when the real question is where a capability belongs or whether the environment architecture should change.
- Use `cpss-prompt-project-reviewer` for an independent audit of an existing persistent instruction system.
- Use Skill Creator when an installable Skill must be initialized, validated, packaged, or updated.

## Boundaries

- Do not treat Project instructions as a dumping ground for reusable methods.
- Do not turn Skills into stores of volatile domain facts.
- Do not invent tools, permissions, persistence, connectors, files, or platform behavior.
- Do not force the user through a long intake form if the current requirements are already sufficient.

## Output

When asked to create or revise persistent instructions, return the complete copy/paste-ready instruction artifact. Keep commentary and implementation notes outside the artifact unless they belong in the durable instructions themselves.
