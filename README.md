# Mobile App IPA GitHub Builder

[![Skill validation](https://img.shields.io/badge/skill-validated-22c55e)](SKILL.md)
[![Flutter](https://img.shields.io/badge/Flutter-supported-02569B?logo=flutter)](SKILL.md)
[![Swift](https://img.shields.io/badge/Swift%20%2F%20iOS-supported-F05138?logo=swift)](SKILL.md)
[![Works with AI](https://img.shields.io/badge/AI-Claude%20%7C%20Gemini%20%7C%20Codex%20%7C%20Cursor%20%7C%20Copilot-111827)](SKILL.md)

حزمة مهارات محمولة لتحويل فكرة قصيرة إلى تطبيق Flutter أو Swift/iOS مصمم باحتراف، مرفوع إلى GitHub، ومبني كـ IPA عبر GitHub Actions.

## ماذا تفعل؟

تعطي الـ AI فكرة بسيطة مثل:

> أريد تطبيقًا يحفظ ملفات IPA ويفحص توافقها مع LiveContainer.

ثم تطلب التقنية فقط إذا كانت غير محددة، وتنفذ التصميم، المشروع، الاختبارات، المستودع، GitHub Actions، وIPA artifact.

## حزمة التصميم

قبل كتابة الواجهة، يقرأ الـ AI هذه الوحدات بالترتيب:

1. Flutter Design Taste
2. Mobile App UI/UX Pro Max
3. Flutter Custom Design System
4. Flutter Improve Design
5. Flutter UI Design — thienqo

هذه الوحدات المرفقة هي implementations أصلية محمولة لأدوار التصميم المذكورة، وليست ادعاءً بأنها ملفات رسمية لمؤلفين خارجيين. إذا كانت النسخ الرسمية مثبتة في بيئة AI، يمكن للـ AI قراءتها مع الوحدات المرفقة.

## الاستخدام مع أي AI

- **Claude:** وجّه Claude إلى `adapters/claude/CLAUDE.md`.
- **Gemini:** استخدم `adapters/gemini/GEMINI.md`.
- **Codex:** استخدم `adapters/codex/AGENTS.md`.
- **Cursor:** انسخ `adapters/cursor/.cursorrules` إلى جذر مشروعك.
- **GitHub Copilot:** انسخ `adapters/copilot/copilot-instructions.md` إلى `.github/copilot-instructions.md`.
- **أي AI آخر:** اطلب منه قراءة `SKILL.md` ثم كل الملفات داخل `skills/` قبل التنفيذ.

## مثال طلب

```text
أريد تطبيق Flutter لمستخدمي LiveContainer يختبر توافق IPA، يحفظ الملفات محليًا، ويولد تقريرًا قابلًا للمشاركة. ابدأ بالـ MVP وانشره على GitHub وابنِ IPA عبر Actions.
```

## ما الذي يتم تسليمه؟

- واجهة Mobile-first مع Design System.
- حالات loading/empty/error/success/disabled.
- Assets وأيقونة حقيقية.
- مشروع Flutter أو Swift قابل للبناء.
- README وLICENSE وGitHub Actions.
- IPA غير موقّع وSHA-256 بعد نجاح macOS workflow.

IPA الناتج غير موقّع عادةً؛ ثبّته عبر SideStore أو AltStore أو أداة توقيع تملكها.

## المجلدات

```text
SKILL.md                         المهارة الرئيسية
skills/                          وحدات التصميم الخمس
adapters/                        تعليمات Claude/Gemini/Codex/Cursor/Copilot
examples/                        أمثلة طلبات جاهزة
templates/                       قوالب Design Direction
```

## المساهمة

اقترح تحسينًا أو أضف module جديدة مع الحفاظ على: تصميم قابل للاستخدام، عدم تسريب الأسرار، بناء قابل للتكرار، وعدم الادعاء باستخدام مهارة غير موجودة.
