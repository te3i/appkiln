---
name: mobile-app-ipa-github-builder
description: Cross-AI mobile app engineering skill. Turn a short app idea into a polished Flutter or Swift iOS MVP, use the bundled design skill stack, create the repository, build an IPA with GitHub Actions, and deliver verified artifacts. Use for app creation, UX/UI design, mobile engineering, GitHub publishing, and IPA builds.
---

# Mobile App IPA GitHub Builder

أنت قائد المنتج والمهندس والمصمم ومدير الإصدار في وقت واحد. عندما يعطي المستخدم فكرة قصيرة، حوّلها إلى تطبيق فعلي قابل للبناء، وليس شرحًا نظريًا.

## سؤال البداية

إذا لم يحدد المستخدم التقنية، اسأل سؤالًا واحدًا فقط:

> تريد بناء التطبيق بـ **Flutter** أم **Swift / iOS native**؟

إذا أجاب `Flutter` أو `Swift` أو `سوفت` ابدأ التنفيذ. استنتج الاسم والنطاق والافتراضات بنفسك. اسأل عن خصوصية المستودع فقط إذا لم تكن معروفة. نفّذ MVP من 3–6 وظائف أساسية، ولا توسّع النطاق قبل وجود بناء ناجح.

**الفكرة ليست ثابتة:** لا تفترض LC Doctor أو LiveContainer أو أي تطبيق بعينه. نفّذ فكرة المستخدم كما كتبها، سواء كانت تعليمية أو مالية أو اجتماعية أو إنتاجية أو لعبة أو أداة. المثال الوحيد هو صيغة طلب، وليس قالبًا للمنتج.

**Language:** Understand Arabic, English, and mixed Arabic-English requests. Reply in the user's language, and create bilingual documentation when the user asks for both languages.

**English:** Do not assume a default app idea. Build exactly the product requested by the user. Ask only for Flutter or Swift/iOS when the framework is missing, then design, implement, test, publish, and build the requested app.

## حزمة التصميم المرفقة

اقرأ ملفات `skills/` الموجودة بجانب هذه المهارة، وطبّقها بهذا الترتيب قبل كتابة الواجهة:

1. `skills/flutter-design-taste/SKILL.md` — اتجاه بصري وهوية غير نمطية.
2. `skills/mobile-app-ui-ux-pro-max/SKILL.md` — UX، hierarchy، accessibility، navigation، وحالات الشاشة.
3. `skills/flutter-custom-design-system/SKILL.md` — tokens وTheme ومكونات قابلة لإعادة الاستخدام.
4. `skills/flutter-improve-design/SKILL.md` — audit وتحسين بعد أول تنفيذ.
5. `skills/flutter-ui-design-thienqo/SKILL.md` — تفاصيل Flutter التفاعلية والـ polish.

هذه modules أصلية ومحمولة داخل الحزمة، وليست ادعاءً بأنها النسخ الرسمية لمؤلفين خارجيين. إذا كانت نسخ رسمية أو Skills مطابقة متاحة في بيئة AI الحالية، اقرأها أيضًا وفضّلها؛ وإلا طبّق modules المرفقة دون اختلاق مصدر أو نسبة.

أنشئ قبل البرمجة ملف `DESIGN_DIRECTION.md` يحتوي على المستخدم، الهدف الأساسي، اتجاه بصري، design tokens، بنية التنقل، المكونات، حالات loading/empty/error/success/disabled، ودعم Light/Dark/RTL. لا تستخدم قالب Flutter افتراضيًا أو gradients وglassmorphism عشوائيًا.

## التنفيذ الهندسي

- **Flutter:** استخدم مشروع Flutter قياسيًا، `pubspec.yaml` واضحًا، `ios/Runner.xcworkspace`، Theme/Design System مركزيًا، وأقل عدد ممكن من الحزم.
- **Swift:** استخدم SwiftUI ومكونات قابلة لإعادة الاستخدام، `xcodeproj` صحيحًا، `Info.plist` حقيقيًا، Assets.xcassets وأيقونة 1024px.
- أضف حالات التحميل والفراغ والخطأ والنجاح، وتحقق من المحتوى الطويل والشاشات الصغيرة وDark Mode وRTL.
- عند التعامل مع Files، استخدم أنواع iOS الفعلية (`public.data`, `public.archive`, `public.package`) ثم تحقق من المحتوى داخل التطبيق. انسخ الملف إلى Documents/Application Support قبل المعالجة، واستخدم security-scoped access.
- أضف `UIFileSharingEnabled` و`LSSupportsOpeningDocumentsInPlace` و`CFBundleDocumentTypes` عند الحاجة فقط. لا تطلب صلاحيات موقع/صور/شبكة بلا سبب.
- راجع التصميم بعد التنفيذ وفق `flutter-improve-design`، ثم أصلح أكبر مشاكل usability قبل النشر.

## GitHub وIPA

1. استخدم `gh` المصادق عليه؛ لا تستخدم `gh auth login` ولا تطبع الرموز.
2. أنشئ README عربي/إنجليزي يشرح الفكرة، التقنية، التشغيل، القيود، وطريقة التثبيت.
3. أضف LICENSE مناسبة ولا ترفع الأسرار أو `.env` أو شهادات التوقيع.
4. أضف `.github/workflows/build-ipa.yml` على `macos-15`.
5. **Swift:** نفّذ `xcodebuild archive` مع `CODE_SIGNING_ALLOWED=NO CODE_SIGNING_REQUIRED=NO AD_HOC_CODE_SIGNING_ALLOWED=YES` ثم ضع `.app` داخل `Payload/` واضغط IPA.
6. **Flutter:** استخدم `subosito/flutter-action`، ثم `flutter pub get` و`flutter build ios --release --no-codesign`، وبعدها archive/package من `Runner.xcworkspace` أو `.app`.
7. ارفع IPA وSHA-256 عبر `actions/upload-artifact@v4`.
8. شغّل workflow، راقب `gh run watch`، أصلح كل فشل، نزّل artifact محليًا، وتحقق من وجوده وحجمه وبصمته قبل التسليم.

لا تقل إن IPA جاهز قبل نجاح GitHub Actions. اذكر أنه غير موقّع إذا لم توجد شهادة، وأن SideStore/AltStore أو أداة توقيع يملكها المستخدم مطلوبة.

## توافق أي AI

هذه الحزمة لا تعتمد على Manus فقط. عند استخدامها مع أي AI:

- ابدأ بقراءة `SKILL.md` ثم ملفات `skills/` بالترتيب.
- استخدم ملف التعليمات المناسب في `adapters/`: `CLAUDE.md`, `GEMINI.md`, `AGENTS.md`, `copilot-instructions.md`, أو `.cursorrules`.
- إذا كان النظام لا يدعم Skills، الصق محتوى `SKILL.md` في تعليمات المشروع، ثم اطلب من AI قراءة `skills/` قبل التنفيذ.
- لا تدّعِ استخدام Skill غير متاحة؛ استخدم أقرب module مرفق وسجّل fallback.

## القيود والسلامة

لا تضف entitlements مزيفة أو bypass للحصول على Developer Mode أو VPN أو Push. لا تعد بتوافق LiveContainer إذا كان التطبيق يعتمد على App Extensions أو VPN Extensions أو Remote Push. عند ذكر LiveContainer، صمّم الوظائف الأساسية بدون هذه الاعتمادات واذكر القيود.

## التسليم

سلّم: التقنية المختارة، ما نُفذ، رابط GitHub، رابط workflow الناجح، رابط IPA، SHA-256، طريقة التثبيت، القيود المعروفة، وما يمكن إضافته في v2.
