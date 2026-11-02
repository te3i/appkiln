# About AppKiln

> **Official website:** [appkiln.pages.dev](https://appkiln.pages.dev)<br>
> **Releases:** [github.com/te3i/appkiln/releases](https://github.com/te3i/appkiln/releases)

AppKiln is a universal mobile product build skill for turning a product idea into a polished Flutter or Swift application. It is designed for AI-assisted development, but it is not tied to one model or coding environment.

## What AppKiln coordinates

AppKiln connects five focused design modules through one shared execution contract:

1. **Visual direction** establishes the product personality, palette, typography, spacing, surfaces, and visual signature.
2. **Experience architecture** turns the idea into a clear flow, screen hierarchy, states, accessibility rules, and interaction requirements.
3. **Design-system engineering** converts the direction into reusable tokens, themes, components, navigation, feedback, and state patterns.
4. **Design improvement** audits the real implementation and fixes hierarchy, consistency, usability, accessibility, responsive behavior, and content issues.
5. **Interaction polish** finishes the build with responsive details, safe-area behavior, keyboard handling, motion, feedback, and implementation quality.

## What makes it different

AppKiln assigns clear ownership to each design layer instead of asking one generic instruction to handle everything at once. Each stage produces a written handoff, and `DESIGN_DIRECTION.md` keeps the visual and interaction decisions consistent while the app is implemented.

The same workflow can be used with Claude, Gemini, Codex, Cursor, GitHub Copilot, OpenCode, or another capable coding agent through the adapter instructions in [`adapters/`](../adapters/).

## Delivery promise

A completed AppKiln workflow keeps the repository and release process visible. Depending on the requested platform, it can prepare Flutter Android APK output, Flutter iOS IPA output, Swift iOS IPA output, or both. The delivery report includes the selected technology, implementation summary, GitHub URL, successful workflow URL, artifact URL, SHA-256 checksum, installation instructions, limitations, and possible v2 additions.

## Website

The public [AppKiln official website](https://appkiln.pages.dev) presents the product, workflow, and design philosophy. The repository keeps the skill source and documentation organized.

## Releases

AppKiln uses GitHub Releases for meaningful milestones. Release notes identify what changed in the core orchestration, five-module design pipeline, AI adapters, delivery workflows, documentation, website, and known limitations. This keeps the public history understandable and avoids publishing random snapshots.
