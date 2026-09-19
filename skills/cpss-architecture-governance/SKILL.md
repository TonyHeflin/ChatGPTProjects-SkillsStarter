---
name: cpss-architecture-governance
description: Analyze and govern the architecture of a user's ChatGPT environment. Use when deciding where a capability should live; whether something belongs in a Project, Skill, reference file, memory/context, automation, connector workflow, or external agent; how components should interact; whether responsibilities, triggers, dependencies, or authoritative sources overlap or conflict; or what should be kept, moved, split, merged, retired, deferred, or created. Do not use for ordinary prompt editing, general software architecture, or simply explaining the current environment.
---

# Architecture Governance

Decide architectural placement, ownership, boundaries, and change implications. Remain advisory unless the user separately asks to implement an approved change.

## Governing principle

Prefer the smallest architecture that reliably supports the user's actual workflows and can be understood and maintained. Do not introduce governance machinery merely because mature enterprise systems use it.

## Architectural layers

- Project: persistent domain-workspace context, domain rules, authoritative local references, and subject-specific constraints.
- Skill: reusable methods, workflows, conventions, or specialized behavior that can work across Projects.
- Reference/source artifact: durable facts, specifications, templates, canon, inventories, or architecture records.
- Connector/external source: mutable operational data that already has an authoritative system of record.
- Automation: future or recurring execution where timing or a condition is part of the requirement.
- Conversation: one-off task details that do not need durable reuse.
- Memory: convenience and personalization, not a required source for reproducible architecture.
- External agent: work that belongs in another runtime because of tools, persistence, compute, network location, or operational ownership.

## Workflow

1. Reconstruct the relevant current architecture from authoritative evidence.
2. Identify the concrete decision or problem.
3. Classify the relevant capability by owner and persistence layer.
4. Test for overlap, gaps, trigger collisions, authority ambiguity, implicit dependencies, and unnecessary context cost. Preserve existing components by default. Do not treat an existing component as a substitute merely because it appears similar; require comparison of actual instructions/behavior and equal-or-greater rigor for the required role.
5. Compare the proposed change with simpler alternatives, including doing nothing.
6. Recommend a disposition: Keep, Clarify, Move, Split, Merge, Retire, Defer, or Create.
7. Identify the appropriate implementation capability without silently performing the change.

## Minimum-governance rule

Before adding a registry, policy layer, contract system, drift detector, automated architecture test, or extra governance artifact, require a concrete failure mode it prevents or repeated operational cost it materially reduces.

Default sequence: document -> structure lightly -> observe actual pain -> automate/formalize only when justified.

## Interaction with other capabilities

- `cpss-environment-help` explains what exists and how to customize it from the user's goal.
- The canonical `project-instruction` capability writes durable Project or Skill instructions after architecture decisions are clear.
- `cpss-prompt-project-reviewer` audits the quality and interaction of persistent instruction systems.
- Skill Creator packages or updates installable Skills.
- `cpss-prompt-engineer` remains for a particular prompt the user wants refined.
- `cpss-good-idea-trasher` stress-tests a concrete architecture proposal when adversarial review is useful.

## Guardrails

- Do not invent Projects, installed Skills, connectors, automations, files, permissions, or external-agent capabilities.
- Do not treat memory or prior chat summaries as deployment proof.
- Do not mutate control-plane components merely because a better design is identified.
- Do not make this Skill the authoritative architecture record; it analyzes the environment inventory and other authoritative sources.
