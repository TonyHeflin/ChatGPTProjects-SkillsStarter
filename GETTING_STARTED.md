# Getting Started

ChatGPT Projects & Skills Starter can be used with either a new ChatGPT account or an account that already contains Projects, Skills, files, and other work.

The bootstrap is intentionally **non-destructive**. On an existing account it performs a quick collision preflight before creating anything. It does not reorganize or modify your existing setup.

## Fastest path

1. Open ChatGPT in the account you want to configure.
2. Start a normal new chat. Keep this browser tab open for the entire bootstrap.
3. Paste this message:

   > Bootstrap my ChatGPT environment using the instructions at https://github.com/TonyHeflin/ChatGPTProjects-SkillsStarter/blob/main/BOOTSTRAP.md. Treat that file and the source files it links to as authoritative. Load linked files only when needed. If you cannot read a link, tell me exactly which file to paste or upload.

4. Follow ChatGPT's instructions.

When a setup step would navigate away from the bootstrap conversation, ChatGPT should tell you to open a **new browser tab** and leave the bootstrap tab open.

## If you already use ChatGPT heavily

That is supported.

Before creating the starter's Projects or Skills, the bootstrap should check only for collisions with the components it intends to create. It should not perform a broad cleanup or assume that existing components are inferior, obsolete, or safe substitutes.

An existing component may satisfy a starter requirement only when its actual behavior can be inspected and shown to provide **equal or greater rigor** for the required role. Similar names or descriptions are not enough.

Existing components remain unchanged unless you explicitly choose otherwise.

## If something fails during setup

Do **not** restart the bootstrap.

The bootstrap is designed to keep a state ledger and treat most failures as local to the affected component. It should continue independent work, record the blocker, and resume automatically when the blocker is resolved.

After fixing a problem or completing a requested UI action, return to the original bootstrap chat and reply with something simple such as **"fixed"**, **"done"**, or **"continue"**. ChatGPT should read the existing ledger and resume from the first actionable incomplete item without repeating completed work.

If ChatGPT instead tries to restart the whole setup, point it back to the **Resumable bootstrap state** section in `BOOTSTRAP.md`.

## If ChatGPT cannot read the GitHub link

Open [BOOTSTRAP.md](BOOTSTRAP.md), copy its contents, and paste them into the bootstrap chat.

If a later linked file cannot be retrieved, paste or upload that individual Markdown file when ChatGPT asks for it.

## Skills availability

Native personal Skills are currently available to eligible ChatGPT Business, Enterprise, Healthcare, and Edu users, subject to workspace settings and product availability. Other accounts can still use the Project-based foundation, but the bootstrap must not claim that the full Skill layer was installed.

Skills are not available in every ChatGPT account or workspace configuration. The bootstrap should inspect the current environment instead of assuming Skill creation or installation is available.

When Skills are available and ChatGPT creates one from the supplied definition, you may be shown an **Install** prompt or button. You must approve that installation. ChatGPT should not claim a Skill is installed before approval or verified installed state.

If you need to inspect Skills manually, use a new browser tab and open **Sidebar → Plugins → Skills**. The current interface can show categories such as Installed and Created by me.

## Projects

Projects are created separately from the bootstrap conversation.

When the bootstrap asks you to create one, it should first give you the complete Project name and instructions, then tell you to:

1. Open a **new browser tab** and leave the bootstrap chat open.
2. Open ChatGPT in the new tab.
3. Select **New project** in the sidebar.
4. Enter the supplied Project name and finish creating it.
5. Open the newly created Project.
6. Open the Project's **more-options menu (•••) → Project settings**.
7. Paste the supplied Project instructions and save them.
8. Return to the original bootstrap tab and continue.

Do not move the bootstrap conversation into the new Project.

## GitHub access

You do not need to connect your GitHub account to use this public repository. The repository is simply the readable source for the bootstrap.

A connected GitHub account may let ChatGPT work directly with repositories you can access, but available read/write/create actions depend on the current connector and workspace. The bootstrap should inspect those actions rather than assume them.

## Managed-workspace option

Eligible workspace administrators may also be able to import and synchronize plugin marketplaces from GitHub. That can simplify distribution of Skills/plugins in managed environments, but it is optional and does not replace Project creation or the universal bootstrap path above.
