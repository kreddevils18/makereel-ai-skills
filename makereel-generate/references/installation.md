# Connect a creator's assistant

The user is a creator, not a developer. Install only an officially released, prebuilt Makereel connector for their operating system. The official release entry point is [Makereel Quickstart](https://makereel.kienhoang.me/docs/quickstart).

If the connector is already installed, use it; do not replace a working installation as part of ordinary slideshow creation. If no public installer is available, report that exact prerequisite and stop setup. Do not clone private application source, install Go, compile the CLI, start servers, invent download URLs, or install similarly named npm packages.

## Installation and sign-in

1. Identify native macOS, Windows, or Linux and CPU architecture. WSL is a separate Linux environment, not the native Windows installation. Use the official installer matching the environment in which the assistant runs.
2. Let the user approve installer/security prompts. A security warning is not permission to disable protections. Open a new terminal after installation and verify `makereel --version` and `makereel --help`.
3. Run `makereel auth status`. If sign-in is needed, ask the user to run `makereel auth login` and approve the browser device code themselves. Use `--no-browser` only when opening the browser fails. Do not request credentials in chat or read credential files.
4. Verify account access with `makereel profiles list`. Explain an empty account list as a setup requirement in Makereel; do not create an account without the user's request.
5. Finish setup without importing images, analyzing posts, generating content, scheduling, or publishing. Those are separate user decisions.

## Optional local MCP connection

An assistant that can execute the CLI directly does not also need MCP. For clients that use local MCP tools, launch the installed native executable with the single argument `mcp` after sign-in.

Find the executable using `command -v makereel` on macOS/Linux or `(Get-Command makereel).Source` in Windows PowerShell. Use that absolute path in the client's supported configuration. Preserve spaces in Windows paths and escape backslashes in JSON. Do not copy Unix paths into Windows configuration or launch a native Windows executable from WSL as if it were a Linux binary.

Follow the client's current installation documentation rather than assume every client accepts the same JSON:

- [Claude Code local MCP](https://code.claude.com/docs/en/mcp#option-3-add-a-local-stdio-server)
- [Local MCP server guide](https://modelcontextprotocol.io/docs/develop/connect-local-servers)

The connection reuses the user's browser-authorized CLI session. Do not place tokens in configuration. There is no hosted Makereel MCP URL for a web-only chat connection. Opening documentation in a chat shares guidance, not account access.
