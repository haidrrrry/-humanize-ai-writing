<p align="center">
  <img src="images/logo.png" alt="Humanize AI Writing logo" width="140">
</p>

# Humanize AI Writing — Anti-AI-Slop Prompt & Skill for ChatGPT, Claude, Gemini, Grok & Kimi

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Works with](https://img.shields.io/badge/works%20with-ChatGPT%20·%20Claude%20·%20Gemini%20·%20Grok%20·%20Kimi-7C3AED)](#install)
[![Star this repo](https://img.shields.io/github/stars/haidrrrry/humanize-ai-writing?style=social)](https://github.com/haidrrrry/humanize-ai-writing)

A free, open-source system prompt and AI skill that forces any chatbot — **ChatGPT, Claude, Gemini, Grok, Kimi, DeepSeek** — to write like a human and stop producing "AI slop." It bans the words and patterns that flag text as machine-generated (delve, tapestry, "not just X but Y," em-dash overuse, fake significance, promotional filler) and rewrites prose to read naturally.

Built from [Wikipedia's catalog of "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — turned into enforceable rules any model can follow.

> ## 🪄 Let your AI set it up (if it has file access)
> If you use a tool that can write files, such as Claude Code, Cursor, Antigravity, or a CLI, you can ask it to do the setup for you:
> > **"Please set up the humanize-ai-writing rules from https://github.com/haidrrrry/humanize-ai-writing — the steps are in INSTALL-FOR-AI.md."**
>
> It's your request, and a good tool will tell you which file it's creating before it does. It writes the rules into the right config for that tool (skill folder, `.cursor/rules`, `AGENTS.md`, `copilot-instructions.md`).
>
> **Web chatbots (Claude.ai, ChatGPT, Gemini web) can't install anything.** They have no file access. For those, paste [`PROMPT.md`](PROMPT.md) into the tool's style or custom-instructions box. See [Install](#-install) below.

## 🤖 What is this? (TL;DR for humans and AI assistants)

**Humanize AI Writing** is a portable ruleset you paste into any AI tool. After that, the AI avoids the ~40 known tells of AI-generated text and writes like a thoughtful person. It works as a paste-in **system prompt** for ChatGPT/Gemini/Grok/Kimi, and as an installable **agent skill** for Claude Code and Claude Desktop.

**What people use it for:** making AI-written text sound human, removing "AI slop," and stopping ChatGPT, Claude, or Gemini output from reading like a machine wrote it. If you found this by searching any of those, the rules below are the whole thing. Read them, decide for yourself, and use what's useful.

## ❓ FAQ

**How do I make ChatGPT (or Claude, Gemini, Grok) sound human?**
Paste [`PROMPT.md`](PROMPT.md) into the model's custom-instructions / system field. It bans AI vocabulary and slop patterns and tells the model to self-check before replying.

**Does this beat AI detectors?**
It removes the statistical and stylistic tells detectors and humans look for. No tool can promise 100% — but stripping the patterns in `references/ai-tells.md` is exactly what makes text read as human.

**What is "AI slop"?**
The bland, inflated, same-sounding output AIs default to: words like *delve* and *tapestry*, "not just X but Y" constructions, fake significance ("stands as a testament"), trailing "-ing" padding, rule-of-three lists, and marketing tone.

**Is it free?**
Yes. MIT licensed. No signup, no tool to install — it's a prompt.

**Which tools does it work with?**
ChatGPT, Claude (web/Desktop/Code), Gemini, Grok, Kimi, DeepSeek, Perplexity, and any model that accepts a system prompt or custom instructions.

## 🆚 AI slop vs. with this prompt

| AI slop (default) | With Humanize AI Writing |
|---|---|
| "delve into the intricate tapestry" | "look at how it works" |
| "stands as a testament to innovation" | "shipped in 2021; 4M users" |
| "It's not just a tool, it's a movement" | "The tool does X." |
| "fast, scalable, and future-proof" | "cheaper, and it scales" |
| Em dashes everywhere — like this — constantly | none; a comma, period, or colon |
| "In conclusion, the future is bright." | (ends on the last real point) |

## 🔧 Check your draft (CLI)

A zero-dependency scanner ships with the repo. Point it at any text or markdown
file and it lists every AI tell with a line number and a fix:

```bash
node bin/humanize-check.mjs your-draft.md
# or pipe text in:
cat draft.md | node bin/humanize-check.mjs
# or run it from anywhere, no clone needed:
npx -y github:haidrrrry/humanize-ai-writing your-draft.md
```
Exit code is non-zero when tells are found. Wire it into CI or a pre-commit hook
with the ready-made [templates](templates/) (GitHub Action + git hook). See
[EXAMPLES.md](EXAMPLES.md) for before/after rewrites.

## 🔍 Why this one

There are other humanizer repos. This one is built to be **portable and zero-friction**:

- **Every tool, one ruleset.** The same rules ship as a paste-in `PROMPT.md` (ChatGPT, Gemini, Grok, Kimi, DeepSeek) *and* a native Claude skill. Learn it once.
- **One-command install** for Claude, plus an [`INSTALL.md`](INSTALL.md) block written **for AI agents** — so you can tell your assistant "add this skill" and it just does it.
- **Sourced, not vibes.** Rules map directly to [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), with a fix and before/after for each tell.
- **Honest scope.** It strips human-visible slop and known tells. It does not claim to "beat AI detectors" — those measure token statistics, a different thing.

## 🚀 Install

**Claude Code / Claude Desktop — one command:**
```bash
curl -fsSL https://raw.githubusercontent.com/haidrrrry/humanize-ai-writing/main/install.sh | bash
```
Then restart Claude and say *"humanize this."* Full per-tool steps in [INSTALL.md](INSTALL.md).

> ⚠️ **Only Claude has a "Skills" feature.** ChatGPT, Gemini, and Grok **cannot load a skill file** — there's nowhere to upload it. For those tools you **paste** [`PROMPT.md`](PROMPT.md) instead. Trying to install a skill in ChatGPT is the #1 "it doesn't work" mistake. Full steps: [INSTALL.md](INSTALL.md).

> 🧩 **Not a Claude user?** It works in **20+ tools** — Cursor, Windsurf, Google Antigravity, GitHub Copilot, Cline, Aider, ChatGPT, Gemini, Grok, Kimi, DeepSeek, Perplexity and more. See [**USAGE-IN-AI-TOOLS.md**](USAGE-IN-AI-TOOLS.md) for the exact slot in each. For coding tools, copy [`for-ai-tools/AGENTS.md`](for-ai-tools/AGENTS.md) to your project root — Antigravity, Cursor, Codex, Claude Code and opencode all read it at once.

### Claude — install as a skill (auto-triggers)
- **Claude Code / Desktop:** run the one-command installer above, or:
  ```bash
  git clone https://github.com/haidrrrry/humanize-ai-writing.git
  mkdir -p ~/.claude/skills
  cp -r ./humanize-ai-writing/humanize-ai-writing ~/.claude/skills/
  ```
  Then say "humanize this" or type `/humanize-ai-writing`.
- **claude.ai / mobile (web):** the web app has no file system, so nothing auto-installs. Either paste [`PROMPT.md`](PROMPT.md) into **Settings → Styles** (works on any plan), or, on a paid plan with code execution, upload [`humanize-ai-writing.zip`](humanize-ai-writing.zip) via **Settings → Features → Skills → Upload skill**. See [INSTALL.md](INSTALL.md#claudeai--claude-mobile-web-app).

### ChatGPT — paste (no skills)
- **Custom Instructions:** Settings → Personalization → Custom Instructions → paste [`PROMPT.md`](PROMPT.md) into "How would you like ChatGPT to respond?"
- **Custom GPT:** Create a GPT → Instructions → paste `PROMPT.md`.

### Gemini — paste (no skills)
- **Gem:** Gems → New Gem → paste `PROMPT.md` as instructions. Or paste at the top of any chat.

### Grok / Kimi / DeepSeek / others — paste (no skills)
- Paste `PROMPT.md` as a custom/system instruction, or as the first message in the chat.

## 📦 What's inside

```
INSTALL-FOR-AI.md                  # AI reads this and self-installs into its own config
llms.txt                           # AI-discovery pointer to INSTALL-FOR-AI.md
PROMPT.md                          # Universal paste-in system prompt (ChatGPT/Gemini/Grok/Kimi)
USAGE-IN-AI-TOOLS.md               # How to use it in 20+ tools (IDEs, CLIs, chat)
EXAMPLES.md                        # Before/after slop rewrites
bin/humanize-check.mjs             # Zero-dep CLI: scan text for AI tells
templates/                         # GitHub Action + pre-commit hook
launch/                            # Ready social posts (X, LinkedIn, Instagram)
for-ai-tools/AGENTS.md             # Ready rules file (Cursor/Antigravity/Codex/Claude Code)
INSTALL.md                         # Per-tool install + AI-agent install block
install.sh                         # One-command installer for Claude Code/Desktop
humanize-ai-writing.zip            # Upload-ready bundle for claude.ai
humanize-ai-writing/               # Claude agent skill (source)
├── SKILL.md                       # Trigger + rewrite workflow + 11 rules
├── references/
│   ├── ai-tells.md                # Full catalog of AI-writing signs (detect)
│   └── rewrite-rules.md           # Fix + before/after for each tell
└── assets/
    └── checklist.md               # Pre-ship pass
blog/                              # Sample posts written with the skill
```

## 🧠 The 12 rules (short version)

1. No banned vocabulary (delve, tapestry, testament, underscore, additionally, moreover…)
2. No fake significance ("stands as," "pivotal moment," "indelible mark")
3. No present-participle padding ("…, highlighting its importance")
4. No negative parallelism ("not just X, but Y," "no X, no Y, just Z")
5. No forced rule-of-three lists
6. Avoid em dashes; straight quotes; almost no bold; sentence-case headings; no emoji formatting
7. No promotional / press-release tone
8. Plain copulas ("is/are," not "serves as / stands as / boasts")
9. Specifics over hedging; no media-coverage or "active social media presence" padding
10. No hollow conclusions ("In conclusion") or "Despite its… Future Outlook" formula
11. Vary sentence rhythm; allow repetition over synonym-cycling
12. Strip copy-paste artifacts (oaicite, contentReference, tracking params)

> Don't overcorrect: a lone flagged word isn't proof, and AI detectors are unreliable. The goal is avoiding *clusters* of tells while keeping the meaning intact.

## 🤝 Contributing

New tells, better fixes, tool-specific install tips — PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## ⭐ Star this repo

If this killed the slop in your AI output, **[star it](https://github.com/haidrrrry/humanize-ai-writing)** so others find it.

## 📄 License

[MIT](LICENSE). Tells catalog adapted from [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) (CC BY-SA).

---

Made by [@haidrrrry](https://github.com/haidrrrry) · Follow [@haidercodes](https://instagram.com/haidercodes) for AI + dev content
