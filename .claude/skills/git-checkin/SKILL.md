---
name: git-checkin
description: Commit and push changes when the user says "push", "checkin", or "commit". Only ever works on the dev branch, writes a short natural commit message, and pushes without asking for confirmation.
---

# Git Check-in / Push

When the user says **"push"**, **"checkin"**, or **"commit"**, immediately commit
and push the changes.

- **Only work on the `dev` branch.** Verify the branch first.
  - If `dev` exists, switch to it.
  - If `dev` doesn't exist (locally or on the remote), create it from `main`,
    then switch to it.
  - Never push to any other branch.
- Review the diff and stage the relevant changes.
- Use a **short, natural, professional commit message** describing the actual
  change.
- Never mention **Claude, AI, or AI-generated code** in commits or code
  comments.
- Don't add unnecessary comments; comments should be natural and useful.
- Never force-push unless explicitly requested.
- No confirmation is needed when the user explicitly asks to push/check in.
- After pushing, report the commit hash and a brief summary.
