# Changelog

## v1.0.0

First stable release.

### Core
- 12 hard rules derived from Wikipedia's "Signs of AI writing", covering banned
  vocabulary, fake significance, present-participle padding, negative parallelism,
  rule-of-three, punctuation (em dashes banned), promotional tone, copula
  avoidance, weasel attribution, hollow conclusions, rhythm, and copy-paste
  artifacts.
- "Don't overcorrect" guidance: a lone flagged word is not proof, detectors are
  unreliable; the goal is to avoid clusters of tells while keeping meaning.

### Use it anywhere
- `PROMPT.md`: universal paste-in system prompt for ChatGPT, Gemini, Grok, Kimi,
  DeepSeek, and any chatbot.
- `humanize-ai-writing/`: native Claude skill (Code, Desktop) plus
  `humanize-ai-writing.zip` for claude.ai upload.
- `INSTALL-FOR-AI.md` + `llms.txt`: an agent reads these and self-installs into its
  own config from the repo URL.
- `USAGE-IN-AI-TOOLS.md`: setup steps for 20+ tools.
- `for-ai-tools/AGENTS.md`: ready rules file for Cursor, Antigravity, Codex CLI,
  Claude Code, opencode.

### Tooling
- `bin/humanize-check.mjs`: zero-dependency CLI that scans text for tells and
  prints each with a fix. Run locally or via `npx github:haidrrrry/humanize-ai-writing`.
- `templates/`: GitHub Action and pre-commit hook.

### Docs and assets
- `EXAMPLES.md`: before/after rewrites.
- `blog/`: two sample posts written with the skill.
- `launch/`: ready social posts.
- Logo and social-preview image.
- Issue and pull-request templates, `CONTRIBUTING.md`, MIT `LICENSE`.
