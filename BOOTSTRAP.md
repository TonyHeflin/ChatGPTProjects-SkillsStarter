# ChatGPT Projects & Skills Starter — Bootstrap

Use this repository to establish the starter in the user's **current ChatGPT environment**, whether that environment is new or already in use.

Do not reconstruct, infer, import, or modify the repository owner's personal environment. Use only the generic sources in this repository.

## Goal

Establish a useful foundation built around:

- a **General Analysis / Research** domain Project;
- the canonical **Project Instruction** workspace;
- reusable infrastructure Skills when the account supports them;
- a lightweight environment inventory;
- clear user-facing guidance for extending the environment later.

Do this **non-destructively**.

## Core model

Explain this briefly before setup:

- A **Project is a domain workspace**. It owns persistent context, files/references, and instructions specific to that subject or body of work.
- A **Skill is a reusable capability**. It provides a method or workflow that may be useful across multiple Projects.
- The Project owns the domain context. Skills provide reusable capabilities.

Use simple examples such as Home Lab, Woodworking, Small Business, Writing, or a Hobby Helper Project.

## Canonical sources

Load only the source needed for the current step.

Projects:

- General Analysis / Research: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/projects/general-analysis-research.md
- Project Instruction: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/projects/project-instruction.md

Skills:

- Prompt Engineer: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-prompt-engineer/SKILL.md
- Project Instruction: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/project-instruction/SKILL.md
- Prompt / Project Reviewer: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-prompt-project-reviewer/SKILL.md
- Progressive Interview: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-progressive-interview/SKILL.md
- Architecture Governance: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-architecture-governance/SKILL.md
- Environment Help: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-environment-help/SKILL.md
- Research: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-research/SKILL.md
- Research Validation: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-research-validation/SKILL.md
- Good Idea Trasher: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-good-idea-trasher/SKILL.md
- Document Extraction: https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/skills/cpss-document-extraction/SKILL.md

Inventory template:

- https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/templates/environment-inventory.md

Architecture reference:

- https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/docs/architecture.md

If a URL cannot be retrieved, tell the user exactly which Markdown file is needed and ask them to paste or upload that file. Do not require ZIP archives or rendered office documents.

## Action classes

Before claiming completion, classify each setup action accurately:

- **Agent-executable** — perform it now and verify it.
- **User-mediated** — prepare what you can, then give exact interface steps and continue after the user completes them.
- **Environment-dependent** — inspect the current account/tool surface before deciding what is possible.
- **Unavailable / blocked** — state the limitation and continue independent work where possible.

Never claim a Project, Skill, Library file, connector state, or other component exists unless it was created, observed, or confirmed by the user.

## Mandatory user-interface rule

Whenever the user must perform an interface action:

1. State what has already been prepared.
2. State exactly what the user must do.
3. Give concrete interface steps.
4. Explain what result they should expect.
5. Explain whether the action changes pages or context.
6. Explain how to return and continue bootstrap.

If the action would navigate away from this bootstrap conversation, tell the user to **open a new browser tab first and leave the bootstrap tab open**.

## Step 0 — Record starter version

Read https://raw.githubusercontent.com/TonyHeflin/ChatGPTProjects-SkillsStarter/main/VERSION and record that version in the environment inventory. Treat the repository version as provenance, not proof that every component was successfully installed.

## Step 1 — Quick non-destructive collision preflight

Do this **before creating or installing anything**.

The purpose is not to inventory the whole account or improve the user's existing architecture. The purpose is only to avoid colliding with the starter components about to be created.

### What to check

Check for existing Projects or Skills that could plausibly collide with:

- **General Analysis / Research**;
- **Project Instruction**;
- any of the starter Skills listed above.

Use direct environment inspection when available.

If Projects cannot be inspected directly, ask the user to use a **new browser tab**, review the Projects visible in the ChatGPT sidebar, and report only obvious same-name or same-purpose candidates. If needed, have the user open a candidate Project and use **••• → Project settings** to inspect its instructions. Then have them return to the bootstrap tab.

If Skills cannot be inspected directly but Skills are available in the account, ask the user to use a **new browser tab** and open **Sidebar → Plugins → Skills**. Have them check Installed and Created by me for obvious same-name or same-purpose candidates. Then have them return to the bootstrap tab.

Do not ask for a complete catalog unless a specific collision cannot be resolved without it.

Also make one narrow check for **global Custom Instructions** if the account uses them. The purpose is not to review tone or preferences. Check only for substantive workflow, research, routing, tool-use, clarification, or instruction-authority rules that could materially conflict with the starter. Preserve them unchanged. If they cannot be inspected directly, ask only whether such rules exist and inspect them only when a plausible conflict is identified.

### Collision rule

Existing components are **preserved by default**. Do not rename, delete, rewrite, disable, merge, or otherwise modify them as part of bootstrap.

A similar existing component is **not** automatically a substitute for a starter component.

Only treat an existing component as potentially satisfying a starter requirement after inspecting its actual instructions/behavior and establishing that it provides **equal or greater rigor** for the required role.

Names, titles, descriptions, popularity, age, or apparent intent are not sufficient evidence of equivalence.

### Equal-or-better standard

When evaluating a possible substitute, compare the actual component against the canonical starter definition. At minimum determine whether the existing component:

- covers the same required responsibilities and boundaries;
- does not omit material controls present in the starter definition;
- has trigger conditions at least as precise where triggering matters;
- does not introduce unsupported platform assumptions or hidden dependencies;
- preserves source, freshness, uncertainty, action-boundary, or safety rigor where those are part of the starter role;
- does not create a worse ownership or routing ambiguity elsewhere in the environment.

If the existing component cannot be inspected deeply enough to make that comparison, equivalence is **unproven**.

### Preflight outcomes

For each possible collision, classify it as one of:

- **No collision observed** — proceed with the starter component.
- **Potential overlap; equivalence unproven** — preserve the existing component; do not substitute it.
- **Existing component is materially weaker or different** — preserve it; do not substitute it.
- **Existing component is equal or better** — explain the comparison and ask whether the user wants that component to satisfy the starter role or still wants the canonical starter component separately.
- **Hard conflict** — creating the starter component would create a naming, trigger, instruction, or role conflict that should not be left unresolved. Pause only that component and ask the user how they want to resolve it.
- **Unknown** — visibility is insufficient. Perform the smallest targeted inspection needed before proceeding with that component.

Do not weaken the starter merely to avoid duplication.

### Namespacing

The starter's custom infrastructure Skills use `cpss-` internal names to make provenance clear and reduce direct naming collisions.

**Project Instruction remains canonical and unprefixed**, both as a Project and as its dedicated Skill definition.

Namespacing does not eliminate functional trigger conflicts. Evaluate meaningful trigger overlap separately.

## Step 2 — Create/install infrastructure Skills when supported

Skills availability is environment-dependent. Do not pretend Skills are installed capabilities when the current account does not support them.

When Skill creation is available:

1. Load the canonical `SKILL.md` for the current Skill.
2. Ask ChatGPT/Skill Creator to create that Skill from the supplied definition without silently changing its scope or trigger.
3. If ChatGPT presents an installation prompt/card, tell the user to click **Install**.
4. Do not claim installation before the user approves it or installed state is otherwise verified.
5. If installation requires leaving the current conversation, tell the user to use a new browser tab and return afterward.
6. After creation/installation, perform a **source-fidelity check** before marking the Skill complete. Compare the installed/generated Skill against the canonical repository source for its internal name, trigger description, instruction body, and required supporting references. Do not assume a generated Skill is identical merely because it was created from a prompt.
7. If installed Skill source cannot be inspected well enough to compare, mark fidelity as **unverified** rather than claiming exact installation. Continue only with the user's informed acceptance of that limitation.

If manual inspection is needed, use **Sidebar → Plugins → Skills**.

The platform-provided Skill Creator may be used when available. Do not reproduce or replace its internal implementation.

### Progressive Interview boundary

Progressive Interview is standalone interaction behavior. Do not force it into Project creation, Skill creation, prompt engineering, or any other workflow.

It should activate only when the current response would otherwise dump a large or branching questionnaire on the user. When enough information is known, the original task simply continues.

## Step 3 — Create the foundational Projects

Prepare the complete instructions before asking the user to create a Project.

For each Project that survived preflight without an unresolved collision:

1. Give the user the exact Project name and complete instructions.
2. Tell the user to open a **new browser tab** and leave this bootstrap tab open.
3. In the new tab, tell the user to open ChatGPT and select **New project** from the sidebar.
4. Tell the user to create the Project using the supplied name.
5. After creation, tell the user to **open the newly created Project**.
6. Inside the Project, tell the user to open **••• → Project settings**.
7. Tell the user to paste the supplied Project instructions and save them.
8. Tell the user to return to the original bootstrap tab and confirm completion.

Do not tell the user to move this bootstrap conversation into the new Project.

The foundational Projects are:

- **General Analysis / Research**
- **Project Instruction**

## Step 4 — Create lightweight self-documentation

Create a Markdown file named **ChatGPT Environment Architecture & Inventory** using the supplied template.

Record only meaningful architecture that actually exists, plus clearly marked unresolved or blocked items. Do not turn it into a complete chat history, account export, or configuration database.

Prefer Library as the durable home when available. If verification requires navigation, tell the user to open a new tab, choose **Library** from the sidebar, verify the file, and return to the bootstrap tab.

Never put secrets or inappropriate private account details into a public repository.

## Step 5 — Explain customization

After the foundation is ready, explain that **Environment Help** is the plain-language front door for customization.

The user should be able to say things like:

- “I want ChatGPT to help me restore motorcycles.”
- “I keep doing this workflow repeatedly.”
- “Should this become a Project or a Skill?”
- “How should I organize this work?”

The user should not need to understand the architecture before asking for help.

Then ask whether they would like to create another Project. Offer **Hobby Helper** as an approachable example plus **Something else** and **Not now**.

Do not force Progressive Interview into this flow. If the conversation naturally reaches a point where many dependent questions would otherwise be dumped at once, Progressive Interview may activate on its own.

## Step 6 — Validate before declaring completion

Verify or accurately classify:

- collision preflight completed for starter components;
- no existing component was modified without explicit user direction;
- any substituted existing component was actually shown to be equal or better;
- installed starter Skills/capabilities and any blocked Skill setup;
- source-fidelity status for each installed starter Skill;
- General Analysis / Research Project;
- canonical Project Instruction Project;
- environment inventory and its durable location;
- Progressive Interview's independent trigger behavior;
- Environment Help's ability to explain customization;
- every user-mediated step included exact UI and context-transition guidance;
- repository version provenance is recorded;
- GitHub-source access or its paste/upload fallback is working.

Finish with a concise reconciliation:

- completed;
- user action still required;
- environment-dependent or blocked;
- intentionally omitted;
- unresolved collisions, if any.
