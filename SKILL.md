---
name: mobile-app-ipa-github-builder
description: Build and publish mobile app ideas from a short natural-language brief. Use when the user wants an iOS Swift app or Flutter app created, uploaded to GitHub, and built as an IPA through GitHub Actions.
---

# Mobile App → GitHub → IPA

حوّل فكرة التطبيق المختصرة إلى مشروع قابل للبناء، ولا تتعامل معها كإجابة نظرية. ابدأ بسؤال واحد فقط إذا لم يحدد المستخدم التقنية:

> تريد بناء التطبيق بـ **Flutter** أم **Swift / iOS native**؟

اقبل إجابة مثل `Flutter` أو `Swift` أو `سوفت`. إذا حدد المستخدم التقنية مسبقًا، ابدأ التنفيذ مباشرة. لا تسأل عن تفاصيل يمكن استنتاجها؛ اختر اسمًا مناسبًا للتطبيق، وبنية MVP عملية، وواجهة مرتبة، ثم وثّق الافتراضات في README.

**متطلب UX/UI إلزامي:** قبل كتابة الواجهة، استخدم حزمة مهارات التصميم التالية بالترتيب عندما تكون مثبتة في الجلسة. الهدف هو إنتاج واجهة مميزة وغير نمطية، وليس قالب Flutter افتراضيًا:

1. **Flutter Design Taste** — اختيار الاتجاه البصري والهوية والـ art direction.
2. **Mobile App UI/UX Pro Max** — تجربة الاستخدام، بنية الشاشات، سهولة الوصول، وتدفق التنقل.
3. **Flutter Custom Design System** — تحويل الاتجاه إلى tokens ومكونات Flutter قابلة لإعادة الاستخدام.
4. **Flutter Improve Design** — مراجعة وتحسين الواجهة بعد أول تنفيذ.
5. **Flutter UI Design — thienqo** — تطبيق أنماط Flutter المتقدمة والتفاصيل التفاعلية.

إذا لم تكن إحدى المهارات الخمس متاحة، لا تتظاهر باستخدامها: استخدم `ui-ux-pro-max` المتاح كمرجع أساسي، وطبّق نفس الأدوار يدويًا، ثم أكمل التنفيذ.

## سير العمل الإلزامي

1. **فهم الفكرة وتثبيت النطاق**
   - حوّل الفكرة إلى MVP قابل للتشغيل، مع 3–6 وظائف أساسية فقط في الإصدار الأول.
   - راجع قيود LiveContainer إذا ذكرها المستخدم: تجنب App Extensions وVPN Extensions وPush Notifications والصلاحيات الخاصة، إلا إذا طلبها صراحة.
   - اختر iOS 17+ افتراضيًا للمشروع الجديد ما لم يطلب المستخدم إصدارًا أقدم.
   - اسأل عن خصوصية مستودع GitHub فقط إذا لم تكن معروفة؛ لا تنشئ مستودعًا عامًا افتراضيًا عندما قد يحتوي المشروع على أسرار.

2. **اختيار مسار التنفيذ**
   - **Swift / iOS native:** أنشئ مشروع SwiftUI واضحًا مع `xcodeproj` أو استخدم مشروعًا قائمًا. أضف `Info.plist` حقيقيًا، Assets.xcassets وأيقونة، و`Document Types` عندما يكون التطبيق يتعامل مع Files.
   - **Flutter:** أنشئ مشروع Flutter قياسيًا مع `pubspec.yaml` و`ios/Runner.xcworkspace`. لا تخلط SwiftUI بواجهة Flutter إلا لضرورة واضحة. استخدم حزمًا مستقرة ومحدودة، وحدث `Info.plist` و`CFBundleDocumentTypes` عند الحاجة.
   - لا تستخدم خدمات مدفوعة أو أسرارًا داخل المستودع. ضع مفاتيح API في GitHub Secrets أو اجعل الميزة اختيارية.

3. **تصميم UX/UI ثم التنفيذ**
   - نفّذ مرحلة تصميم قصيرة قبل البرمجة: حدّد المستخدم الأساسي، أهم إجراء في الشاشة الأولى، بنية التنقل، حالات الشاشة، ونظام التصميم.
   - استخدم طبقة **Flutter Custom Design System** أو أقرب بديل لتحديد design tokens: الألوان الدلالية، الخطوط، أحجام النص، المسافات، نصف قطر الحواف، الظلال، حالات المكونات، والتباين.
   - صمّم Mobile-first مع دعم RTL عند الحاجة، ومناطق لمس مريحة، ونصوص واضحة، وDark Mode قابل للقراءة.
   - أضف حالات loading وempty وerror وsuccess وdisabled، ورسائل خطأ قريبة من العنصر المتسبب بها.
   - استخدم SF Symbols في Swift أو Material Icons المتناسقة في Flutter، ولا تستخدم Emoji كأيقونات واجهة.
   - اجعل الحركة قصيرة وهادفة وتحترم Reduce Motion، وراجع الشاشة الأولى والانتقال والتنقل قبل كتابة منطق البيانات.

4. **جودة التطبيق قبل الرفع**
   - ابنِ واجهة فعلية، لا شاشة placeholder فقط.
   - أضف حالات التحميل والخطأ والفراغ، واسم الملف/البيانات بعد الاستيراد، وحفظًا محليًا عندما يتوقع المستخدم أن تبقى البيانات بعد إغلاق التطبيق.
   - عند استيراد ملفات من Files: لا تعتمد على UTI مخصص غير مضمون. استخدم أنواع iOS الفعلية مثل `public.data` و`public.archive` و`public.package`، ثم تحقق من المحتوى داخل التطبيق. انسخ الملف إلى Documents/Application Support قبل معالجته، واستخدم security-scoped access.
   - أضف `UIFileSharingEnabled` و`LSSupportsOpeningDocumentsInPlace` و`CFBundleDocumentTypes` فقط عندما يحتاج التطبيق ملفات المستخدم. لا تطلب صلاحيات موقع/صور/شبكة بلا حاجة.
   - أضف أيقونة 1024px واسم عرض واضح، وتحقق من RTL إذا كانت الواجهة عربية.

5. **اختبارات محلية قبل GitHub**
   - افحص صيغة Swift/Dart و`Info.plist` و`git diff --check`.
   - شغّل اختبارات الوحدات إن وجدت.
   - تحقق أن كل ملف مستخدم في المشروع مضاف فعلًا إلى target، وأن Assets وInfo.plist مربوطان بالبناء.
   - لا تدّعِ أن IPA بُني قبل نجاح GitHub Actions على macOS.

6. **إنشاء المستودع والرفع**
   - استخدم GitHub CLI المصادق عليه عبر `gh`. لا تستخدم `gh auth login` ولا تطبع الرموز.
   - أنشئ مستودعًا باسم واضح، أضف README وLICENSE مناسبة، ثم commit وpush إلى `main`.
   - لا ترفع `.env` أو مفاتيح أو شهادات توقيع أو provisioning profiles سرية.
   - اذكر في README أن IPA الناتج غير موقّع إذا كان البناء بدون شهادة، وأن المستخدم يحتاج SideStore/AltStore أو توقيعًا يملكه.

7. **GitHub Actions وبناء IPA**
   - أضف `.github/workflows/build-ipa.yml` أو `build.yml` يعمل على `macos-15`.
   - **Swift:** استخدم `xcodebuild archive` مع `CODE_SIGNING_ALLOWED=NO CODE_SIGNING_REQUIRED=NO AD_HOC_CODE_SIGNING_ALLOWED=YES`، ثم انسخ `.app` إلى `Payload/` واضغطه باسم `.ipa`.
   - **Flutter:** استخدم `subosito/flutter-action`، ثم `flutter pub get` و`flutter build ios --release --no-codesign`، وبعدها archive/package بالطريقة نفسها من `Runner.xcworkspace` أو `.app` الناتج.
   - ارفع IPA وملف SHA-256 كـ artifact باستخدام `actions/upload-artifact@v4`.
   - شغّل workflow بعد push، راقب `gh run watch`, وأصلح أي فشل بدل تسليم رابط فاشل.
   - بعد النجاح نزّل artifact إلى مسار محلي، تحقق من وجود IPA وحجمه وSHA-256، ثم سلّم رابط GitHub Actions ورابط الملف المحلي.

## قواعد مهمة

- لا تقل إن التطبيق سيعمل داخل LiveContainer إذا كان يعتمد على صلاحيات أو Extensions لا تنتقل إلى Guest App. اذكر القيد بوضوح واقترح بديلًا.
- لا تضف bypass أو entitlements مزيفة للحصول على صلاحيات iOS. Developer Mode وVPN وPush لا يمكن للتطبيق منحها لنفسه.
- عند فشل اختيار ملف من Files داخل LiveContainer، افحص أولًا أنواع المستندات، ثم الحفظ في Documents، ثم اطلب من المستخدم تفعيل Fix File Picker في إعدادات Guest App فقط كحل احتياطي.
- إذا كان المشروع يحتاج صورة أو أيقونة، أنشئ أصلًا محليًا مناسبًا وأضفه إلى Assets؛ لا تترك التطبيق بأيقونة افتراضية.
- إذا كان المطلوب أكثر من 6 وظائف كبيرة، نفّذ MVP أولًا ثم أنشئ قائمة v2 بدل توسيع المشروع بلا اختبار.

## التسليم النهائي

اذكر باختصار:

- التقنية المختارة.
- ما تم تنفيذه فعليًا.
- رابط المستودع.
- رابط GitHub Actions الناجح.
- رابط IPA artifact أو الملف المحلي.
- طريقة التثبيت والتوقيع.
- أي قيود معروفة.

لا تقل "تم الإطلاق" إذا لم ينجح البناء أو لم يتم رفع المستودع. إذا فشل البناء، اعرض الخطأ وأصلحه قبل التسليم.
