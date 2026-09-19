---
description: Check whether the Antigravity (agy) CLI is installed and ready
allowed-tools: Bash
---

Run the setup check for the agy CLI:

```bash
node "${CLAUDE_PLUGIN_ROOT}/scripts/agy-companion.mjs" setup
```

Print the result verbatim. If agy is not installed, tell the user to install it with the command the companion printed. On macOS with Homebrew that is:

```
brew install --cask antigravity-cli
```

Elsewhere, the vendor installer applies:

```
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

Do not run either installer yourself, and never run the vendor installer where Homebrew already manages `agy`: it replaces the cask's symlink with a plain binary and breaks `brew upgrade`.

Then re-run this command to verify.
