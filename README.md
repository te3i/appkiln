# AppKiln — Universal Mobile Build Skill
> English-only landing page: [Open the AppKiln landing page](https://github.com/te3i/appkiln/blob/main/docs/index.html)
[![Skill validation](https://img.shields.io/badge/skill-validated-22c55e)](SKILL.md)
[![Flutter](https://img.shields.io/badge/Flutter-supported-02569B?logo=flutter)](SKILL.md)
[![Swift](https://img.shields.io/badge/Swift%20%2F%20iOS-supported-F05138?logo=swift)](SKILL.md)
[![Any AI](https://img.shields.io/badge/AI-Claude%20%7C%20Gemini%20%7C%20Codex%20%7C%20Cursor%20%7C%20Copilot-111827)](SKILL.md)
## Overview
AppKiln is a universal mobile app engineering skill. Describe any app idea, and the AI will turn it into a polished Flutter or Swift mobile MVP. It automatically connects the five bundled design skills, selects the strongest visual direction for the product, implements the app, publishes it to GitHub, and builds the requested APK or IPA through GitHub Actions.
Example:
```text
Build a Flutter expense tracker with categories, reports, and local backup. Use the complete five-module design stack, publish the project to GitHub, and deliver a verified APK.
```
The example is not a fixed product. Replace it with any educational, social, financial, health, productivity, gaming, file utility, or project-specific idea.
## Automatic five-module design pipeline
Before writing the interface, the AI reads and connects these modules in order:
1. Flutter Design Taste
2. Mobile App UI/UX Pro Max
3. Flutter Custom Design System
4. Flutter Improve Design
5. Flutter UI Design — thienqo
The result is a complete `DESIGN_DIRECTION.md`, a coherent design system, reusable components, accessible states, responsive screens, and an implementation refined through a design audit.
## Platform delivery
- **Flutter + Android:** builds and uploads a verified APK.
- **Flutter + iOS:** builds and uploads a verified IPA.
- **Swift + iOS:** builds and uploads a verified IPA.
- **Both artifacts:** creates both platform workflows when the user requests both APK and IPA.
Every delivery includes the GitHub repository, successful Actions workflow, artifact URL, SHA-256 checksum, installation instructions, and a concise implementation report.
## Use with any AI
- Claude: `adapters/claude/CLAUDE.md`
- Gemini: `adapters/gemini/GEMINI.md`
- Codex: `adapters/codex/AGENTS.md`
- Cursor: `adapters/cursor/.cursorrules`
- GitHub Copilot: `adapters/copilot/copilot-instructions.md`
- Any other AI: read `SKILL.md`, then every file under `skills/`, before coding.
## Repository contents
The main files are `SKILL.md`, `skills/`, `adapters/`, `examples/`, and `templates/`.
