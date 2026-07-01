# Install — Humanize AI Writing

**Read this first.** There are two completely different ways to use this, and
which one you need depends on your tool:

| Tool | Method | What you use |
|---|---|---|
| **Claude Code / Desktop** | Install as a **Skill** (auto-triggers) | the `humanize-ai-writing/` folder |
| **Claude.ai / mobile (web)** | A **Style** (any plan), or upload the skill **`.zip`** (paid) | `PROMPT.md` or the `.zip` |
| **ChatGPT** | **Paste** instructions (no skill system) | `PROMPT.md` |
| **Gemini** | **Paste** instructions (no skill system) | `PROMPT.md` |
| **Grok / Kimi / DeepSeek / others** | **Paste** instructions (no skill system) | `PROMPT.md` |

> ⚠️ **ChatGPT, Gemini, and Grok do not have a "skills" feature.** You cannot
> upload a skill file to them — there is nowhere to put it. They only accept a
> pasted system prompt / custom instruction. Use [`PROMPT.md`](PROMPT.md). This is
> the #1 reason people think "it doesn't work" — they tried to install a skill in
> a tool that has no skills. Paste the prompt instead.

---

## Claude — install as a skill

Skills only exist in Claude. Pick your Claude surface:

### Claude Code (terminal)
One command:
```bash
curl -fsSL https://raw.githubusercontent.com/haidrrrry/humanize-ai-writing/main/install.sh | bash
```
This copies the skill to `~/.claude/skills/humanize-ai-writing`. Restart Claude
Code. Then type `/humanize-ai-writing` or say "humanize this."

Manual version:
```bash
git clone --depth 1 https://github.com/haidrrrry/humanize-ai-writing.git
mkdir -p ~/.claude/skills
cp -r humanize-ai-writing/humanize-ai-writing ~/.claude/skills/
```

### Claude Desktop
Same as above — Claude Desktop reads `~/.claude/skills/`. Run the one-command
installer, then restart the app.

### Claude.ai / Claude mobile (web app)
The web app has no file system, so it can't run the installer or the CLI, and a
chatbot there can't "install" anything for you. You have two supported ways to make
the style stick:

**Option 1: a Style (works on any plan, recommended for web):**
1. Copy the contents of [`PROMPT.md`](PROMPT.md).
2. In Claude.ai: **Settings → Styles → Create style** (or use a Project's custom
   instructions).
3. Paste `PROMPT.md` in, save, and select that style when you write.

**Option 2: upload it as a Skill (Pro / Max / Team / Enterprise with code
execution):**
1. Download [`humanize-ai-writing.zip`](humanize-ai-writing.zip).
2. **Settings → Features → Skills → Upload skill**, select the `.zip`.
3. Say "humanize this" in a chat.

> The skill upload must be a **`.zip`**, not a `.skill` file. If you don't have a
> paid plan or code execution, use Option 1.

---

## ChatGPT — paste the prompt

ChatGPT has no skills. Use one of:

- **Custom Instructions (applies everywhere):** Settings → Personalization →
  Custom Instructions → paste all of [`PROMPT.md`](PROMPT.md) into
  *"How would you like ChatGPT to respond?"* → Save.
- **A Custom GPT (a dedicated humanizer):** Explore GPTs → Create → in
  *Instructions*, paste `PROMPT.md` → Save. Now that GPT always de-slops.

## Gemini — paste the prompt

- **A Gem:** Gemini → Gems → New Gem → paste `PROMPT.md` as the instructions →
  Save. Use that Gem when you want humanized writing.
- Or paste `PROMPT.md` as your first message in any chat.

## Grok / Kimi / DeepSeek / Perplexity / Copilot / Cursor

No skills here either. Paste [`PROMPT.md`](PROMPT.md) as a system/custom
instruction if the tool has that field, otherwise paste it as the first message
of the chat.

---

## For AI agents (a user told you to "add this skill")

If you are an AI assistant and the environment is **Claude Code / Desktop**:
```bash
git clone --depth 1 https://github.com/haidrrrry/humanize-ai-writing.git /tmp/hmz \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/hmz/humanize-ai-writing ~/.claude/skills/ \
  && echo "installed: ~/.claude/skills/humanize-ai-writing"
```
Then confirm `ls ~/.claude/skills/humanize-ai-writing` shows `SKILL.md`.

If the environment is **not Claude** (no `~/.claude/skills`, e.g. you are ChatGPT
or Gemini), you cannot install a skill. Instead read `PROMPT.md` from the repo and
apply its rules to everything you write from now on.

---

## Verify it works (any tool)
Ask the model to write a short paragraph, then: *"humanize it, remove AI slop."*
It should drop words like *delve* and *tapestry*, kill "not just X but Y", and
read like a person wrote it. Compare to `humanize-ai-writing/assets/checklist.md`.
