# Contributing

Useful contributions are welcome.

The most valuable reports are concrete:

- a setup step that no longer matches the current ChatGPT interface;
- a bootstrap step that makes an unsafe assumption about an existing account;
- a Skill trigger that overlaps or collides with another capability;
- a Project/Skill boundary that fails in real use;
- an instruction that is ambiguous, stale, or materially weaker than intended;
- a simpler implementation that preserves the same rigor.

## Issues

When reporting a problem, include:

1. What you were trying to do.
2. What account/workspace context matters, if any.
3. What step or file you followed.
4. What happened.
5. What you expected to happen.

Do not include passwords, access tokens, private account data, customer data, or other sensitive information.

## Pull requests

Keep changes narrow and explain the behavior they are intended to improve. If a change affects bootstrap behavior, Project/Skill ownership, trigger conditions, or user-mediated interface steps, explain the failure mode it addresses.

The Markdown files in this repository are canonical. Do not add generated DOCX/PDF/archive copies as parallel sources of truth.
