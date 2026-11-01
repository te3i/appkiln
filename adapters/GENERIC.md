# Generic AI Adapter

Use this file with any AI model, coding agent, or IDE assistant that does not have a dedicated adapter.

## Project contract

Read the root [`SKILL.md`](../SKILL.md) first, then read every file under [`skills/`](../skills/) in the order specified there. Treat the five modules as one pipeline with explicit ownership and handoffs.

## Required outputs

Before UI implementation, create `DESIGN_DIRECTION.md` with the product brief, visual direction, experience architecture, screen specifications, design tokens, component contract, state contract, design audit, interaction polish, and accessibility decisions.

Before delivery, verify the selected technology, source structure, reusable design system, screen states, tests, GitHub Actions workflow, APK or IPA artifact, artifact size, and SHA-256 checksum.

## Model-agnostic rules

- Infer the product structure and strongest visual direction from the user's idea.
- Ask only for missing technology or artifact choices that cannot be inferred.
- Keep the five module responsibilities separate and preserve their handoffs.
- Use the appropriate runner and build workflow for Android APK, iOS IPA, or both.
- Publish the complete project to GitHub when requested.
- Report exact repository, workflow, artifact, checksum, and installation information.
