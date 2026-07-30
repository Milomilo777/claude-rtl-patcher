# Changelog

All notable changes to this project are documented here, newest first. Format loosely follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## Unreleased

- Broadened documentation and metadata to explicitly cover Urdu, Pashto, Sindhi, Kurdish (Sorani), Dhivehi, and Yiddish, not just Persian, Arabic, and Hebrew — the underlying fix already works at the Unicode bidi-algorithm level and was never actually limited to three languages.
- Added an Urdu translation (`README-UR.md`).
- Rewrote the fallback-prompt section and `CLAUDE.md` to be upfront about what the tool patches, instead of instructing an AI assistant to misrepresent the target application to route around its own safety behavior.
- Corrected the "spoof Apple's ASAR Integrity Check" description — that check belongs to Electron, not Apple, and is unrelated to macOS Gatekeeper.
- Added `CONTRIBUTING.md`, `SECURITY.md`, issue/PR templates, and this changelog.

## v1.1.2

- Use a current macOS Intel runner for release builds (#12).

## v1.1.1

- Build release binaries with Node 22 (#11).

## v1.1.0

- Add standalone cross-platform installers (`install.sh` / `install.ps1`) so the patcher can run without Node.js installed (#10).

## Earlier history

Before tagged releases, notable changes included (see `git log` for full detail):

- Interactive CLI, English documentation, Arabic/Hebrew translations, and CI/CD setup.
- Linux and custom install-path support; native Windows support.
- Auto-detection of native RTL support in newer Claude Desktop builds, applying a font-only patch when full RTL isn't needed.
- Fixes for community-reported issues #4–#9 (a `plist@5` ESM-compatibility crash, unsupported Windows MSIX/AppX installs, and a macOS ASAR-integrity/code-signing bug that could leave the app unable to launch after patching).
- Bilingual (Persian/English) GitHub Pages project site.
