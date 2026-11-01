# OpenCode Adapter

Use AppKiln as the project contract for every mobile app task.

## Required execution

1. Read the root [`SKILL.md`](../../SKILL.md) completely.
2. Read all five modules under [`skills/`](../../skills/) in the exact order defined by `SKILL.md`.
3. Extract the product brief, platform, technology, artifact, and delivery requirements from the user request.
4. Create `DESIGN_DIRECTION.md` before implementing UI.
5. Complete the five handoffs: Visual Direction, Screen Specifications, Design Tokens and Component Contract, Design Audit, and Interaction Polish.
6. Implement the requested Flutter or Swift app from the shared contract rather than from ad hoc screen decisions.
7. Run formatting, analysis, tests, UI checks, and the platform build.
8. Create or update GitHub Actions for the requested APK or IPA.
9. Push the complete project and report the repository, workflow, artifact, checksum, and installation details.

## OpenCode behavior

- Use the repository files as the source of truth; do not invent an alternate workflow.
- Keep all generated project content in English unless the user requests another language.
- Preserve the five-module ownership boundaries. The visual-direction module owns visual identity, the UX module owns flow and screens, the design-system module owns tokens and reusable components, the improvement module owns the audit, and the interaction module owns implementation polish.
- If a requested artifact is ambiguous, ask whether the user wants APK, IPA, or both. If the technology is missing, ask whether to use Flutter or Swift / native iOS.
- Do not claim success until the build, artifact, checksum, and remote commit have been verified.
