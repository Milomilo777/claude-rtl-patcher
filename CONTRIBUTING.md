# Contributing

Thanks for considering a contribution to Claude RTL Patcher.

## Before you start

- **Search existing issues and PRs first.** Several past bugs (`plist@5` ESM breakage, Windows MSIX/AppX, macOS integrity/signing) already have history worth reading before you re-report or re-fix them.
- **Keep PRs small and focused.** One fix, one feature, or one translation per PR is much easier to review than a bundle of unrelated changes. If you find several unrelated issues, open several PRs.
- **This tool patches a real installed application in place** (extracts `app.asar`, injects code, repacks it, and re-signs on macOS). Any change to `index.js` or `lib/` should be treated with the same care you'd want from a tool that modifies your own machine.

## Development setup

```bash
git clone https://github.com/<your-fork>/claude-rtl-patcher.git
cd claude-rtl-patcher
npm install
npm test
```

Run the patcher locally against a real or synthetic Claude installation:

```bash
node index.js --restore          # revert an existing patch
node index.js /path/to/app.asar --full   # patch a specific asar directly
```

## Before opening a PR

- `npm test` passes.
- `node --check` on every changed `.js` file.
- If you changed patching/signing/rollback logic, add a regression test — the existing suite mocks `execFileSync` and the `@electron/asar` header API rather than touching a real installed app, so most changes are testable without a real Claude Desktop install.
- If you touched the fallback-prompt text, `CLAUDE.md`, or anything an AI assistant might read and act on: keep it honest about what the tool actually does and what it's patching. Don't add wording designed to make an AI assistant bypass its own safety behavior — see the project history around this for why that matters.

## Translations

New language READMEs (`README-XX.md`) are welcome, especially for RTL languages not yet covered. Please:
- Mirror the structure of `README.md` (or the closest existing translation) so all versions stay roughly in sync.
- Keep code blocks, commands, and the fallback-prompt text in English inside a translated README — only the surrounding prose should be translated.
- Add a link to the new file in the language-switcher line at the top of every other README.

## Reporting security issues

Please don't open a public issue for a security concern (e.g. a way this tool could damage or compromise a user's installed app beyond its documented behavior). See [SECURITY.md](./SECURITY.md).
