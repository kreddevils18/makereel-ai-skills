# Install and connect Makereel

You need a Makereel account, images in your Library, and an AI assistant that can run local tools. You do not need application source code or a development environment.

## 1. Install the Makereel app connector

The Makereel CLI is the small connector your assistant uses to work with your account.

**Release availability:** the creator installers have not been publicly released yet. The skills are available from [kreddevils18/makereel-ai-skills](https://github.com/kreddevils18/makereel-ai-skills), but a new assistant connection also needs the released connector. Do not install an unrelated package with a similar name. The [official Quickstart](https://makereel.kienhoang.me/docs/quickstart) is the entry point for published download links when available.

When a release is available, choose the installer matching your computer:

| Computer | Installer |
| --- | --- |
| Mac | `.pkg`; choose Apple Silicon or Intel to match **Apple menu → About This Mac**. |
| Windows | `.msi`; choose x64 or ARM64 to match **Settings → System → About → System type**. |
| Ubuntu / Debian | `.deb` matching your computer's architecture. |
| Fedora / other RPM-based Linux | `.rpm` matching your computer's architecture. |

Open the installer and follow its prompts. On Linux, use your distribution's package installer. Open a new terminal after installation so it recognizes the `makereel` command. An installer is not a separate graphical slideshow editor; editing happens in your browser.

Homebrew, WinGet, and npm/npx commands must come from a published Makereel release. They are alternatives, not prerequisites. Installing the skills with `npx skills` does not install this connector.

## 2. Sign in

Open **Terminal** on macOS/Linux or **PowerShell** on Windows and run:

```sh
makereel --version
makereel auth login
```

Follow the browser prompt, confirm the displayed device code, and approve the connection yourself. Do not give your assistant your password or a token. If no browser window opens, run `makereel auth login --no-browser` and open the link it prints.

## 3. Install the skills

Follow the [README installation options](README.md#install-the-skills), then restart your assistant if requested.

Ask the assistant:

```text
Check my Makereel connection and show me the accounts and images available.
Do not upload or import anything, analyze a post, create a slideshow, schedule,
or publish anything.
```

If your assistant needs a local tool connection, ask it to follow [Install for agents](INSTALL_FOR_AGENTS.md). A regular ChatGPT, Gemini, or Claude web chat is not connected merely by opening the documentation there.

## 4. Create your first slideshow

[Open Makereel](https://makereel.kienhoang.me/dashboard), add or connect an account, and add images to your Library. Use the [starter prompt](README.md#try-it). Review the proposed content, approve it only when ready, then open the saved draft in Makereel to edit and export.

## Disconnect

To revoke this computer's saved Makereel connection:

```sh
makereel auth logout
```

Previously issued short-lived access may take up to five minutes to expire. Removing the skills or uninstalling the connector alone is not a substitute for signing out.

## Need help?

- **Command not found / not recognized:** confirm the connector was installed, then open a new terminal. Installing just the skills is not enough.
- **Sign-in expired:** run `makereel auth login` again.
- **No account or images:** add them in Makereel before asking the assistant to create a slideshow.
- **An installer triggers a security warning:** stop and verify its publisher and official download source. Do not disable your computer's security protections.
