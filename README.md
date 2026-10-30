# Prototipito

**Turn an app idea into a working MVP in any AI app builder (Lovable, Bolt, v0, Replit Agent, Base44...) without writing the prompts yourself.**

Prototipito is a skill for AI assistants. It interviews non-technical founders in plain language and delivers:

1. **A full MVP spec** the tool reads first as context, without building anything.
2. **A short project brief** for the tool's permanent project instructions.
3. **An ordered sequence of short build prompts**, each with checks to run before the next one.
4. **A closing review prompt** to catch what's missing, inconsistent or insecure.

It works with any AI assistant that can follow a long set of instructions: Claude, ChatGPT, Gemini, or similar.

## Why a sequence instead of one big prompt?

App builders charge for work done, not prompt length. What burns credits is fixing half-built features. Giving the tool the full spec as context first, then small checked steps, keeps the pieces consistent and makes failures easy to locate.

## How it works

A 7-block interview, one block per message, with suggested answers:

1. The problem
2. The main user journey
3. Features and what stays out
4. Who uses the app (roles and permissions)
5. Data (entities, sample records, personal data)
6. External services (real, faked or left out)
7. Look, feel and language

Then a recap and a build plan that Prototipito decides itself: **Step 0** spec (read-only, sent in the tool's chat/plan mode) → **Skeleton** → **Accounts and permissions** → **one prompt per feature** → **review**.

## Key features

- **Plain language in, precise language out.** Interview in the user's language; spec and prompts always in English.
- **Scope protection.** Every feature must pass: "If this were missing, would the app still be useful?"
- **References become specifics.** Style is described in words; no copying other products' branding.
- **Permissions at the data level**, with a "Load demo data" button so they can be tested.
- **Safe by default.** Faked services, empty states, validation, error handling, and a personal-data check.
- **Tool-agnostic.** Tool-specific details (modes, project brief slot, backend, rollback) live in a reference table inside `SKILL.md`.

## Installation

You can use Prototipito in two ways. Both use the same instructions.

### Option 1: the `.skill` file

A `.skill` file is the packaged skill (a zip containing `prototipito/SKILL.md`). Use it in tools that support skills:

- **Claude:** upload the `.skill` file in your skills settings and enable it.
- **Claude Code:** unzip it, or copy the `prototipito/` folder, into your skills directory (for example `~/.claude/skills/`).

### Option 2: paste the content of `SKILL.md`

Works in any AI assistant, even without skill support. Copy the full text of `SKILL.md` and use it as:

- **Custom instructions / system prompt** of a custom assistant (a Custom GPT, a Gemini Gem, a Claude Project, or similar).
- **Project instructions**, if your tool has projects.
- **The first message of a new chat**, followed by your idea. Start with something like: "Follow these instructions to interview me about my app idea."

Tip: if your assistant can't show clickable option cards, Prototipito automatically falls back to numbered lists you can answer with just a number.

## Usage

Once installed (or pasted), tell the assistant what you want to build, for example:

- "Help me plan my app for Bolt."
- "Write the prompts to build this in Lovable."
- "Quiero hacer una app."

Answer the interview, confirm the recap, then paste the generated spec and prompts into your app builder one at a time, running the checks after each step.

## Contributing

Pull requests are welcome, especially updates to the tool reference as builders change their UI and support for additional tools.
