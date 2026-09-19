# ChatGPT Projects & Skills Starter

A guided starter setup for building a more organized, reusable ChatGPT environment around **Projects** and **Skills**.

This is intended for someone who already knows the basics of ChatGPT but wants a cleaner way to organize ongoing work without having to design the architecture themselves.

## The basic idea

**A Project is a domain workspace.**

A Project gives ChatGPT a persistent place to work on a particular subject, responsibility, or body of work. It can contain the instructions that define how ChatGPT should behave in that domain, hold or reference important files and background information, and use reusable Skills when specialized methods are needed.

For example:

- A **Home Lab** Project might contain information about your servers, network, naming conventions, current architecture, and technical constraints. It could use research, document-analysis, or review Skills when needed.
- A **Woodworking** Project might contain information about your tools, preferred materials, shop constraints, active builds, and reference documents. It could use reusable fabrication or research Skills.
- A **Small Business** Project might contain operating rules, recurring responsibilities, important documents, and business-specific context while using general research, extraction, or writing Skills.
- A **Writing** Project might contain goals, audience, source material, terminology, and editorial rules while drawing on reusable research and writing Skills.

**The Project owns the domain context. Skills provide reusable capabilities.**

A research Skill should not need to be rebuilt separately for woodworking, business, and writing. Each Project can use the same research method while supplying its own subject matter and constraints.

## Compatibility

The **Project** foundation can still be useful on accounts where native personal Skills are unavailable. The full Skills layer currently requires an eligible ChatGPT **Business, Enterprise, Healthcare, or Edu** account/workspace and may also depend on workspace settings.

The bootstrap therefore treats Skills as environment-dependent rather than assuming every ChatGPT account can install them. If Skills are unavailable, it should preserve a useful Projects-only foundation instead of pretending the Skill layer was installed.

OpenAI's current Skills availability guidance: https://help.openai.com/en/articles/20001066

## What this starter sets up

The starter provides a small foundation that can grow with you rather than forcing a large structure up front.

It includes:

- **General Analysis / Research** — a broadly useful Project for careful reasoning, comparison, fact checking, research, and evaluation.
- **Project Instruction** — the canonical workspace for designing and maintaining persistent Project and Skill instructions.
- **Prompt Engineer** — helps improve a particular prompt you are working on.
- **Progressive Interview** — prevents ChatGPT from dumping a large questionnaire on you when several dependent clarifying questions are needed.
- **Environment Help** — a plain-language guide for questions such as “How should I organize this?”, “Should this be a Project or a Skill?”, or “I want ChatGPT to help me with this kind of work.”
- Reusable research, review, architecture, validation, and document-analysis capabilities.
- A lightweight inventory so the environment remains understandable as it grows.

You do not need to understand the architecture before using it. The goal is for you to describe what you want to do and let the environment help you decide how to organize it.

## Safe with an existing ChatGPT account

The starter is designed to work **non-destructively** in both new and already-used accounts.

Before creating anything, the bootstrap performs a quick collision check against the Projects and Skills it intends to add. It does **not** perform a broad cleanup or decide that your existing setup should be reorganized.

Existing Projects, Skills, files, instructions, and settings are left unchanged.

If an existing component appears similar to one supplied here, similarity is not enough to substitute it. The bootstrap should only treat an existing component as satisfying a starter requirement when its actual behavior can be inspected and shown to provide **equal or greater rigor** for the required role. If that cannot be established, the existing component is preserved but not assumed to be equivalent.

The starter’s custom infrastructure Skills use `cpss-` internal names where appropriate to make provenance clear and reduce direct naming collisions. **Project Instruction remains canonical and unprefixed.** Namespacing does not eliminate functional trigger conflicts, so the bootstrap still checks for meaningful overlap before installation.

## Project status

This is an early, practical implementation rather than a claim that there is one “correct” way to organize ChatGPT Projects and Skills.

The design is intentionally opinionated, and ChatGPT's features and interface change frequently. Some setup steps may vary by account, plan, or workspace.

> **Testing note:** The self-deployment/bootstrap path currently has very little real-world testing outside the development environment. Treat it as beta, review each step, and report anything that behaves differently in your account.

Useful feedback is welcome, especially:

- setup steps that no longer match the current ChatGPT interface;
- instructions that are unclear or fail in practice;
- Project or Skill boundaries that create real workflow problems;
- collision handling that makes unsafe assumptions;
- simpler approaches that achieve the same result without reducing rigor.

If you encounter a problem, an issue describing what you tried, what happened, and what you expected is especially helpful.

## Getting started

Start with **[GETTING_STARTED.md](GETTING_STARTED.md)**.

The normal setup begins in a regular ChatGPT chat. You give ChatGPT the bootstrap instructions from this repository, and it walks through the setup with you.

Some steps can be performed by ChatGPT. Other steps require you to click something in the ChatGPT interface, such as installing a Skill or creating a Project. When that happens, the bootstrap is designed to tell you exactly what to do and, when necessary, tell you to use a new browser tab so the bootstrap conversation stays open.

The Markdown files in this repository are the source of truth. There is no requirement to download an archive or keep parallel DOCX/PDF copies.

## What this is not

This is not a backup of someone else's ChatGPT account, a preloaded collection of personal Projects, or an attempt to automate every part of the ChatGPT interface.

It provides a reusable starting architecture and the instructions needed to build it in your own account. Your Projects, files, connected accounts, and domain-specific information remain yours to add as needed.

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE).

## Code of Conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). The short version: **don't be a jerk.**

## Privacy, personal information, and connected accounts

> **Important:** Treat AI systems, public repositories, and connected accounts as separate security boundaries.
>
> - Do not paste passwords, API keys, access tokens, recovery codes, or other authentication secrets into ChatGPT or commit them to any repository.
> - Do not put private personal, customer, medical, financial, employment, or organizational information into a **public** repository you control.
> - Before connecting GitHub, Google Drive, email, or another account, review what access you are granting and whether ChatGPT can only read data or can also modify it.
> - Review generated Project instructions and Skill definitions before installing or relying on them. AI can misunderstand requirements, make mistakes, or produce outdated interface guidance.
> - If you create an environment inventory, do not publish private environment-specific details. Store those records somewhere appropriate for your own account.
>
> This project is intended to make ChatGPT easier to organize, not to change the normal responsibility to protect sensitive information and review actions taken on connected accounts.
