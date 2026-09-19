---
description: Check whether the Antigravity (agy) CLI is installed and optionally toggle the stop-time review gate
argument-hint: '[--enable-review-gate|--disable-review-gate]'
allowed-tools: Bash(node:*), AskUserQuestion
---

Run:

```bash
node "${CLAUDE_PLUGIN_ROOT}/scripts/agy-companion.mjs" setup --json $ARGUMENTS
```

If the result says agy is unavailable:
- Tell the user to install agy with the command listed under next steps. On macOS with Homebrew that is `brew install --cask antigravity-cli`; elsewhere it is the vendor installer:

```
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

- Do not run either installer yourself, and never run the vendor installer where Homebrew already manages `agy`: it replaces the cask's symlink with a plain binary and breaks `brew upgrade`.

If agy is already installed:
- Present the final setup output to the user.

Output rules:
- If the review gate was toggled, confirm the change.
- If agy is installed but not authenticated, remind the user to run `agy auth`.
