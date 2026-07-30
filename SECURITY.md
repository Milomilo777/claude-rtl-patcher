# Security Policy

## What this tool does, and why that matters for security reports

Claude RTL Patcher modifies an installed application in place: it extracts `app.asar`, injects CSS/JS, repacks the archive, and — on macOS — recomputes an integrity hash and ad-hoc re-signs the app bundle so it still passes Gatekeeper and Electron's own launch checks. That's inherently higher-stakes than a typical CLI tool, so please report the following as security issues rather than regular bugs:

- A patch or rollback path that could leave `app.asar` or `Info.plist` in a corrupted or inconsistent state (see the project history for real examples: an integrity-hash/plist mismatch after a failed restore, native binaries silently getting packed back into the archive on Windows/Linux).
- Anything that could execute unintended code, escalate privileges, or write outside the detected Claude Desktop install path.
- Any content in this repository (including `CLAUDE.md`, README fallback prompts, or code comments) that instructs an AI coding assistant to bypass sandboxing, misrepresent what it's modifying, or otherwise act outside what the user actually asked for. This project has had this exact problem before; if you see it recur, it's a valid report.

## Reporting a vulnerability

Please use GitHub's private vulnerability reporting instead of a public issue: open the repository's **Security** tab and select **Report a vulnerability**. This creates a private advisory that only maintainers can see until a fix is ready.

If private reporting isn't available to you, open a regular issue with minimal reproduction details and a note that you have a security concern you'd prefer to discuss privately first — a maintainer can follow up.

## Supported versions

This project ships from a single rolling `main` branch (no long-term-support versions). Security fixes are only made against the latest release; please update before reporting an issue you haven't reproduced on the current version.
