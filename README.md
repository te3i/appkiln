# AppKiln — Mobile Build Skill
> English-only landing page with an independent language toggle removed for a consistent experience: [Open the AppKiln landing page](https://github.com/te3i/appkiln/blob/main/docs/index.html)
[![Skill validation](https://img.shields.io/badge/skill-validated-22c55e)](SKILL.md)
[![Flutter](https://img.shields.io/badge/Flutter-supported-02569B?logo=flutter)](SKILL.md)
[![Swift](https://img.shields.io/badge/Swift%20%2F%20iOS-supported-F05138?logo=swift)](SKILL.md)
[![Any AI](https://img.shields.io/badge/AI-Claude%20%7C%20Gemini%20%7C%20Codex%20%7C%20Cursor%20%7C%20Copilot-111827)](SKILL.md)
## Overview
This is not a skill for one specific app and does not contain a default product idea. Describe any app you want, and the AI will turn it into a real Flutter or Swift/iOS MVP. It asks about the technology only when it is unspecified, then applies UX/UI, builds a design system, creates the project, publishes it to GitHub, and produces an IPA through GitHub Actions.
Example:
```text
Build a Flutter expense tracker with categories, reports, and local backup. Use the complete design stack, publish the project to GitHub, and build an IPA.
```
The example is not a fixed product. Replace it with any idea: an educational, social, financial, health, productivity, gaming, file utility, or project-specific app.
## Design skill stack
Before writing the interface, the AI reads these modules in order:
1. Flutter Design Taste
2. Mobile App UI/UX Pro Max
3. Flutter Custom Design System
4. Flutter Improve Design
5. Flutter UI Design — thienqo
These are original modules bundled for the listed design roles, not claims to be official versions by external authors. If official versions are available in the AI environment, they may be read alongside the bundled modules.
## Use with any AI
- Claude: `adapters/claude/CLAUDE.md`
- Gemini: `adapters/gemini/GEMINI.md`
- Codex: `adapters/codex/AGENTS.md`
- Cursor: `adapters/cursor/.cursorrules`
- GitHub Copilot: `adapters/copilot/copilot-instructions.md`
- Any other AI: read `SKILL.md`, then every file under `skills/`, before coding.
## Output
The result includes a real Flutter or Swift project, design direction, reusable components, assets and an icon, tests/checks, an English README and license, GitHub Actions, and a non-signed IPA artifact with SHA-256 after a successful macOS build. Use SideStore, AltStore, or a signing tool you own to install an unsigned IPA.
The main files are `SKILL.md`, `skills/`, `adapters/`, `examples/`, and `templates/`.
