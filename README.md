# Makereel AI Skills

Turn a brief into an editable slideshow with your AI assistant and images from your Makereel Library. Review the slides, images, and caption before approving creation, then finish in the [Makereel editor](https://makereel.kienhoang.me/dashboard).

## Install the skill

Install from the public [kreddevils18/makereel-ai-skills](https://github.com/kreddevils18/makereel-ai-skills)
repository. The skill installs instructions; using Makereel also requires the connector
and a signed-in account described below.

### Claude Code: no Node.js required

In Claude Code:

```text
/plugin marketplace add kreddevils18/makereel-ai-skills
/plugin install makereel@makereel
```

Restart Claude Code if it asks you to. The skill is available as `makereel:generate`.

### Codex, Cursor, and other supported agents

If you already have Node.js/npm installed, open Terminal on macOS/Linux or PowerShell on Windows:

```sh
npx skills add kreddevils18/makereel-ai-skills --skill generate --global
```

Choose your assistant when prompted. The skill is named `generate`. If `npx` is not found, install the current [Node.js LTS](https://nodejs.org/en/download) first, then open a new terminal.

Installing this skill adds instructions to your assistant. It does **not** install the Makereel CLI, sign you in, or grant access to your account. See [installation and sign-in](INSTALL.md) before asking the assistant to create content.

## Try it

Once Makereel is connected, paste this into your assistant:

```text
Use the Makereel generate skill to prepare a 5-slide carousel about
three simple habits for a calmer morning, in English.

Use images from my Makereel Library. Ask which account to use if I have more
than one. Show me the slide text, images, layout, and caption before creating
anything. Wait for my approval. Do not schedule or publish it.
```

For setup help, ask your assistant to follow [Install for agents](INSTALL_FOR_AGENTS.md).

## Included skill

| Skill | What it does |
| --- | --- |
| [generate](makereel-generate/SKILL.md) | Prepare a slideshow from your brief or an approved TikTok reference, review an existing draft, or schedule a draft in your Makereel calendar when you explicitly request it. |

The skill uses images you supply or already have permission to use. It does not generate new images or automatically publish to social networks. Scheduling in Makereel is not social publishing.

## Privacy and approval

Sign in in your browser. Never paste passwords, tokens, or session cookies into chat. An installation or setup request is not permission to import images, analyze a reference post, create a slideshow, schedule, or publish anything.

This repository contains agent instructions and examples, not the Makereel application source. Report skill installation issues through this repository's Issues page; do not attach credentials or private customer content.
