# AppKiln — Universal Mobile Build Skill

![AppKiln Universal Mobile Build Skill](docs/assets/appkiln-banner.svg)

AppKiln turns an app idea into a polished Flutter or Swift mobile MVP. It connects five specialized design skills, selects the strongest product direction automatically, builds the app, publishes it to GitHub, and delivers a verified APK or IPA through GitHub Actions.

[![Skill validation](https://img.shields.io/badge/skill-validated-22c55e)](SKILL.md)
[![Flutter](https://img.shields.io/badge/Flutter-supported-02569B?logo=flutter)](SKILL.md)
[![Swift](https://img.shields.io/badge/Swift%20%2F%20iOS-supported-F05138?logo=swift)](SKILL.md)
[![Android APK](https://img.shields.io/badge/Android-APK-3DDC84?logo=android&logoColor=white)](SKILL.md)
[![iOS IPA](https://img.shields.io/badge/iOS-IPA-000000?logo=apple&logoColor=white)](SKILL.md)
[![GitHub Actions](https://img.shields.io/badge/build-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)](SKILL.md)

## Start with one request

```text
Build a Flutter expense tracker with categories, reports, local backup, and a polished dark mode. Use the complete five-module design pipeline, publish the project to GitHub, and deliver a verified APK.
```

The idea is not a fixed template. Use AppKiln for educational, social, financial, health, productivity, gaming, file utility, or project-specific apps.

## How the pipeline works

![AppKiln five-skill design pipeline](docs/assets/skill-pipeline.svg)

The five modules have explicit ownership and documented handoffs:

| Stage | Module | Owns | Handoff |
|---|---|---|---|
| 1 | [`flutter-design-taste`](skills/flutter-design-taste/SKILL.md) | Visual identity and design direction | Visual Direction |
| 2 | [`mobile-app-ui-ux-pro-max`](skills/mobile-app-ui-ux-pro-max/SKILL.md) | User flow, screens, hierarchy, and accessibility | Screen Specifications |
| 3 | [`flutter-custom-design-system`](skills/flutter-custom-design-system/SKILL.md) | Colors, typography, tokens, buttons, and reusable components | Design Tokens + Component Contract |
| 4 | [`flutter-improve-design`](skills/flutter-improve-design/SKILL.md) | Evidence-based review and quality fixes | Design Audit |
| 5 | [`flutter-ui-design-thienqo`](skills/flutter-ui-design-thienqo/SKILL.md) | Responsive implementation and interaction polish | Interaction Polish |

All handoffs are recorded in one shared [`DESIGN_DIRECTION.md`](templates/DESIGN_DIRECTION.md) contract.

## Repository architecture

![AppKiln repository architecture](docs/assets/architecture.svg)

- [`SKILL.md`](SKILL.md) — the main orchestrator and complete execution contract.
- [`skills/`](skills/) — the five connected design modules.
- [`adapters/`](adapters/) — instructions for Claude, Gemini, Codex, Cursor, and GitHub Copilot.
- [`templates/`](templates/) — the shared design-direction template.
- [`examples/`](examples/) — precise request examples.
- [`docs/`](docs/) — architecture, pipeline, and delivery documentation.

Read the detailed guides:

- [Architecture](docs/architecture.md)
- [Design pipeline](docs/design-pipeline.md)
- [Delivery workflow](docs/workflow.md)

## Platform delivery

- **Flutter + Android:** builds and uploads a verified APK on Ubuntu.
- **Flutter + iOS:** builds and uploads a verified IPA on macOS.
- **Swift + iOS:** builds and uploads a verified IPA on macOS.
- **Both artifacts:** creates both platform workflows when the user requests APK and IPA.

Every delivery includes the GitHub repository, successful Actions workflow, artifact URL, SHA-256 checksum, installation instructions, and a concise implementation report.

## Use with any AI

- Claude: [`adapters/claude/CLAUDE.md`](adapters/claude/CLAUDE.md)
- Gemini: [`adapters/gemini/GEMINI.md`](adapters/gemini/GEMINI.md)
- Codex: [`adapters/codex/AGENTS.md`](adapters/codex/AGENTS.md)
- Cursor: [`adapters/cursor/.cursorrules`](adapters/cursor/.cursorrules)
- GitHub Copilot: [`adapters/copilot/copilot-instructions.md`](adapters/copilot/copilot-instructions.md)

Any other AI should read [`SKILL.md`](SKILL.md), then every file under [`skills/`](skills/), before coding.

## Contributing

Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before changing the workflow or adding a module.
