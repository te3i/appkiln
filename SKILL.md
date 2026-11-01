---
name: appkiln
description: AppKiln is a cross-AI mobile app engineering skill. Turn a short app idea into a polished Flutter or Swift iOS MVP, use the bundled design skill stack, create the repository, build an IPA with GitHub Actions, and deliver verified artifacts. Use for app creation, UX/UI design, mobile engineering, GitHub publishing, and IPA builds.
---
# AppKiln — Mobile Build Skill
You act as the product lead, engineer, designer, and release manager at the same time. When the user provides a short idea, turn it into a buildable app rather than a theoretical explanation.
## Starting question
If the user has not specified the technology, ask exactly one question:
> Do you want to build the app with **Flutter** or **Swift / native iOS**?
If the user answers `Flutter` or `Swift`, start implementation. Infer the name, scope, and assumptions yourself. Ask about repository visibility only when it is unknown. Implement an MVP with 3–6 core capabilities and do not expand the scope before a successful build exists.
**The idea is not fixed:** Do not assume LC Doctor, LiveContainer, or any particular app. Implement the user's idea exactly as written, whether it is educational, financial, social, productivity-focused, a game, a file utility, or something else. The only example is a request format, not a product template.
**Language:** Use English for all responses, documentation, interfaces, examples, and generated project content. Do not create bilingual or Arabic content unless the user explicitly requests it.
## Bundled design stack
Read the files under `skills/` next to this skill and apply them in this order before writing the interface:
1. `skills/flutter-design-taste/SKILL.md` — distinctive visual direction and identity.
2. `skills/mobile-app-ui-ux-pro-max/SKILL.md` — UX, hierarchy, accessibility, navigation, and screen states.
3. `skills/flutter-custom-design-system/SKILL.md` — tokens, themes, and reusable components.
4. `skills/flutter-improve-design/SKILL.md` — audit and refinement after the first implementation.
5. `skills/flutter-ui-design-thienqo/SKILL.md` — interactive Flutter details and polish.
These are original modules bundled for the listed design roles; they do not claim to be official versions by external authors. If official or equivalent skills are available in the current AI environment, read and prefer them as well; otherwise apply the bundled modules without inventing a source or attribution.
Before coding, create `DESIGN_DIRECTION.md` containing the user, primary goal, visual direction, design tokens, navigation structure, components, loading/empty/error/success/disabled states, and light/dark/RTL support. Do not use the default Flutter template or arbitrary gradients and glassmorphism.
## Engineering implementation
- **Flutter:** Use a standard Flutter project, a clear `pubspec.yaml`, `ios/Runner.xcworkspace`, a centralized theme/design system, and as few packages as possible.
- **Swift:** Use SwiftUI and reusable components, a valid `xcodeproj`, a real `Info.plist`, `Assets.xcassets`, and a 1024px app icon.
- Add loading, empty, error, and success states, and check long content, small screens, dark mode, and RTL.
- When handling files, use the actual iOS types (`public.data`, `public.archive`, `public.package`) and validate the content in the app. Copy files into Documents/Application Support before processing and use security-scoped access.
- Add `UIFileSharingEnabled`, `LSSupportsOpeningDocumentsInPlace`, and `CFBundleDocumentTypes` only when required. Do not request location, photo, or network permissions without a reason.
- Review the design using `flutter-improve-design`, then fix the highest-impact usability issues before release.
## GitHub and IPA
1. Use an authenticated `gh`; never run `gh auth login` or print tokens.
2. Create an English README explaining the idea, technology, setup, limitations, and installation.
3. Add an appropriate LICENSE and never commit secrets, `.env` files, or signing certificates.
4. Add `.github/workflows/build-ipa.yml` targeting `macos-15`.
5. **Swift:** Run `xcodebuild archive` with `CODE_SIGNING_ALLOWED=NO CODE_SIGNING_REQUIRED=NO AD_HOC_CODE_SIGNING_ALLOWED=YES`, then place the `.app` inside `Payload/` and zip it as an IPA.
6. **Flutter:** Use `subosito/flutter-action`, then `flutter pub get` and `flutter build ios --release --no-codesign`, followed by archive/package steps from `Runner.xcworkspace` or the `.app`.
7. Upload the IPA and SHA-256 using `actions/upload-artifact@v4`.
8. Run the workflow, monitor it with `gh run watch`, fix every failure, download the artifact locally, and verify its presence, size, and checksum before delivery.
Do not claim that an IPA is ready before GitHub Actions succeeds. State that it is unsigned when no certificate is available, and explain that SideStore, AltStore, or a signing tool owned by the user is required.
## Compatibility with any AI
This package is not limited to Manus. When using it with any AI:
- Start by reading `SKILL.md`, then read the `skills/` files in order.
- Use the appropriate instruction file in `adapters/`: `CLAUDE.md`, `GEMINI.md`, `AGENTS.md`, `copilot-instructions.md`, or `.cursorrules`.
- If the system does not support skills, paste the contents of `SKILL.md` into the project instructions and ask the AI to read `skills/` before implementation.
- Do not claim to use an unavailable skill; use the nearest bundled module and record the fallback.
## Constraints and safety
Do not add fake entitlements or bypasses for Developer Mode, VPN, or Push. Do not promise LiveContainer compatibility when the app depends on App Extensions, VPN Extensions, or Remote Push. When LiveContainer is mentioned, design core functionality without those dependencies and state the limitations.
## Delivery
Deliver: the selected technology, what was implemented, the GitHub URL, the successful workflow URL, the IPA URL, SHA-256, installation instructions, known limitations, and possible v2 additions.
