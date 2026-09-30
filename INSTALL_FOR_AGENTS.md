# Install for agents

Help the user connect their AI assistant to Makereel without a development environment.

1. Read [creator connector setup](makereel-generate/references/installation.md). Check for an existing `makereel` executable before installing anything. Use only an officially released installer; if none is available, explain that setup is blocked instead of compiling from source or guessing a package name.
2. Run `makereel auth status`. Only if sign-in is needed, ask the user to complete `makereel auth login` in their terminal and approve the browser device code. Never read or request passwords, tokens, cookies, or credential files.
3. Confirm that the public `kreddevils18/makereel-ai-skills` repository is accessible. If it is not, report that skill installation is unavailable; do not substitute a different repository. Otherwise install using one method:
   - Claude Code: run `claude plugin marketplace add kreddevils18/makereel-ai-skills`, then `claude plugin install makereel@makereel`.
   - Other supported agents with Node.js/npm: run `npx skills add kreddevils18/makereel-ai-skills --skill '*' --global` (or `--skill generate` when the user wants only that skill) and select the user's agent. In Windows PowerShell, if the shell blocks the npm script shim, use `npx.cmd` rather than weakening the execution policy.
4. Restart or reload the assistant if required. For a client using local MCP instead of CLI commands, follow the bundled setup reference using the installed executable's absolute path and `mcp` argument.
5. Verify with `makereel auth status` and `makereel profiles list`. These are read-only checks. Do not create a sample slideshow, import media, analyze a post, or schedule as an installation test.

Report installation and account access separately. A discovered skill is not proof that the connector is installed, and an installed connector is not proof that the user is signed in. Once ready, offer the [starter prompt](README.md#try-it) and let the user choose what to create.
