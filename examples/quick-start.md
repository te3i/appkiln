# أمثلة عامة / Generic Examples

هذه أمثلة لصيغة الطلب فقط. لا توجد فكرة تطبيق افتراضية داخل المهارة.

## عربي — تطبيق صحة

```text
أريد تطبيق Flutter عربي لتسجيل شرب الماء، مع تذكيرات محلية ورسوم أسبوعية ووضع ليلي. صممه بواجهة حديثة، ارفع المشروع إلى GitHub وابنِ IPA عبر Actions.
```

## English — Finance app

```text
Build a Swift iOS app for tracking freelance invoices. Include clients, invoice status, local persistence, PDF export, and a polished accessible UI. Publish it to GitHub and build an IPA with Actions.
```

## عربي/English — Photo utility

```text
أريد تطبيق Flutter يضغط الصور دفعة واحدة / Build a Flutter app that batch-compresses photos, shows before/after size, and exports the results. Use the full design stack and deliver a verified IPA.
```

## Expected behavior / السلوك المتوقع

1. يسأل AI عن Flutter أو Swift فقط إذا لم تحدد التقنية.
2. يقرأ حزمة التصميم الخمس وينشئ `DESIGN_DIRECTION.md`.
3. ينفذ فكرة المستخدم نفسها، بدون استبدالها بمثال جاهز.
4. يبني MVP مع حالات الخطأ والتحميل والفراغ.
5. ينشئ GitHub Actions ويصلح فشل البناء.
6. يسلم GitHub URL وActions URL وIPA وSHA-256.
