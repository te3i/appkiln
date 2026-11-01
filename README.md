# AppKiln — Mobile Build Skill

> صفحة تعريف ثنائية اللغة مع زر تبديل مستقل: [افتح AppKiln بالعربية والإنجليزية](https://te3i.github.io/appkiln/)

[![Skill validation](https://img.shields.io/badge/skill-validated-22c55e)](SKILL.md)
[![Flutter](https://img.shields.io/badge/Flutter-supported-02569B?logo=flutter)](SKILL.md)
[![Swift](https://img.shields.io/badge/Swift%20%2F%20iOS-supported-F05138?logo=swift)](SKILL.md)
[![Any AI](https://img.shields.io/badge/AI-Claude%20%7C%20Gemini%20%7C%20Codex%20%7C%20Cursor%20%7C%20Copilot-111827)](SKILL.md)

## العربية

هذه ليست مهارة لتطبيق واحد، ولا تحتوي فكرة منتج افتراضية. اكتب أي فكرة تطبيق تريدها، وسيحوّلها الـ AI إلى MVP حقيقي بـ Flutter أو Swift/iOS، بعد أن يسألك عن التقنية إذا لم تحددها. بعدها ينفذ UX/UI، يبني Design System، ينشئ المشروع، يرفعه إلى GitHub، ويصنع IPA عبر GitHub Actions.

مثال عام:

```text
أريد تطبيق Flutter عربي لتسجيل المصاريف، مع تصنيفات وتقارير ونسخ احتياطي محلي. استخدم حزمة التصميم كاملة، ارفع المشروع إلى GitHub، وابنِ IPA.
```

المثال ليس منتجًا ثابتًا؛ يمكنك استبداله بأي فكرة: تطبيق تعليمي، اجتماعي، مالي، صحي، إنتاجي، لعبة، أداة ملفات، أو تطبيق خاص بمشروعك.

## English

This is a product-agnostic skill. It does not assume LC Doctor, LiveContainer, or any default app idea. Describe any app you want, and the AI will turn it into a real Flutter or Swift/iOS MVP. It asks for the framework only when it is missing, applies the bundled design stack, creates the project, publishes it to GitHub, and builds a verified IPA with GitHub Actions.

Example:

```text
Build a Swift iOS habit tracker with streaks, local persistence, reminders, and a polished accessible dark mode. Publish it to GitHub and build an IPA through Actions.
```

## Design skill stack / حزمة التصميم

قبل كتابة الواجهة، يقرأ الـ AI الوحدات التالية بالترتيب:

1. Flutter Design Taste
2. Mobile App UI/UX Pro Max
3. Flutter Custom Design System
4. Flutter Improve Design
5. Flutter UI Design — thienqo

هذه modules أصلية محمولة لأدوار التصميم المذكورة، وليست ادعاءً بأنها النسخ الرسمية لمؤلفين خارجيين. إذا كانت نسخ رسمية متاحة في بيئة AI، يمكن قراءتها مع الوحدات المرفقة.

## Use with any AI / الاستخدام مع أي AI

- Claude: `adapters/claude/CLAUDE.md`
- Gemini: `adapters/gemini/GEMINI.md`
- Codex: `adapters/codex/AGENTS.md`
- Cursor: `adapters/cursor/.cursorrules`
- GitHub Copilot: `adapters/copilot/copilot-instructions.md`
- Any other AI: read `SKILL.md`, then every file under `skills/`, before coding.

## Output / التسليم

The result includes a real Flutter or Swift project, design direction, reusable components, assets and icon, tests/checks, README and license, GitHub Actions, and a non-signed IPA artifact with SHA-256 after a successful macOS build. Use SideStore, AltStore, or a signing tool you own to install an unsigned IPA.

الملفات الرئيسية هي `SKILL.md` و`skills/` و`adapters/` و`examples/` و`templates/`.
