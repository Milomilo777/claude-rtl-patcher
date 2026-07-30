<div align="center">
  <img src="./assets/preview.png" alt="Claude RTL Patcher Preview" width="100%">
  
  <h1>🌟 Claude RTL Patcher</h1>
  <p><strong>الأداة التلقائية الأفضل لدعم النصوص من اليمين إلى اليسار (RTL) والخطوط الجميلة في تطبيق Claude لسطح المكتب.</strong></p>
  <p>العربية · الفارسية · العبرية · الأردية · البشتو · السندية · الكردية (السورانية) · الديفيهية · اليديشية</p>

  [![npm version](https://badge.fury.io/js/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![npm downloads](https://img.shields.io/npm/dm/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  [![GitHub stars](https://img.shields.io/github/stars/m4tinbeigi-official/claude-rtl-patcher.svg?style=social&label=Star)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/stargazers)

  ✨ *تم تطبيق خاصية RTL بواسطة Rick Sanchez، وتم استخدام خط Vazirmatn إحياءً لذكرى صابر راستيكردار.* ✨

  [🇺🇸 Read in English](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README.md) | [🇮🇷 نسخه فارسی (Persian)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-FA.md) | [🇮🇱 קרא בעברית (Hebrew)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-HE.md) | [🇵🇰 اردو میں پڑھیں (Urdu)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-UR.md)
</div>

---

هذه أداة مفتوحة المصدر وتلقائية تقوم بإضافة الدعم الكامل للنصوص التي تُكتب من اليمين إلى اليسار **(RTL)** وخط **Vazirmatn** الجميل مباشرة إلى **تطبيق Claude الرسمي لسطح المكتب** (على أنظمة macOS و Windows و Linux).

وتعمل على إصلاح محاذاة النص المكسورة للعربية والفارسية والعبرية والأردية والبشتو والسندية والكردية (السورانية) والديفيهية واليديشية — حتى تتمكن من الدردشة مع Claude بكل سلاسة. يعمل هذا الإصلاح على مستوى خوارزمية bidi في يونيكود (`unicode-bidi: plaintext`)، وليس بمعالجة كل لغة على حدة، لذا فهو غير مقتصر على اللغات الثلاث التي بدأ بها هذا المشروع.

🎉 هذا المشروع **[منشور رسمياً على سجل NPM العالمي](https://www.npmjs.com/package/claude-rtl-patcher)**!

> **وضع الكشف التلقائي:** إصدارات Claude Desktop الأحدث تعرض RTL بشكل صحيح تلقائياً بالفعل. عند اكتشاف ذلك، تطبق الأداة **خط Vazirmatn فقط** وتترك الاتجاه/المحاذاة دون تغيير. أما في الإصدارات الأقدم (التي لا تدعم RTL أصلياً)، فلا تزال تُطبَّق حزمة الترقيع الكاملة (الخط + RTL). يمكنك أيضاً فرض وضع معين يدوياً باستخدام `--font-only` أو `--full`.

## 🚀 التثبيت بنقرة واحدة (موصى به)

لست بحاجة إلى تنزيل أو تثبيت أي شيء يدوياً. فقط افتح نافذة الأوامر في نظامك (CMD / PowerShell / Mac Terminal) والصق هذا الأمر السحري:

```bash
npx claude-rtl-patcher
```

*(تحتوي الأداة على واجهة تفاعلية جميلة ستقوم تلقائياً باكتشاف نظام التشغيل الخاص بك، وإنشاء نسخة احتياطية، وحقن أكواد CSS، وعلى macOS إعادة توقيع التطبيق والتحقق منه ليبقى قابلاً للتشغيل، كل ذلك في ثوانٍ معدودة.)*

بمجرد الانتهاء، أغلق تطبيق Claude بالكامل (`Cmd + Q` أو `Ctrl + Q`) ثم افتحه مرة أخرى.

### المثبّت المستقل (لا يتطلب Node.js)
يتم بناء ملفات تنفيذية للإصدارات تلقائياً لأنظمة macOS وWindows وLinux. بعد نشر إصدار، قم بتنزيل الملف المطابق أو شغّل أمر الإقلاع:

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.sh | bash

# Windows PowerShell
irm https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.ps1 | iex
```

يقوم البناء المستقل بتثبيت الأداة للمستخدم الحالي، واكتشاف نظام التشغيل ومسار Claude، وإنشاء نسخة احتياطية، وتشغيل نفس تدفق الترقيع التفاعلي. تثبيتات Windows MSIX/AppX تبقى غير مدعومة لأن ملفات حزمتها غير قابلة للكتابة.

### فرض وضع معين
```bash
npx claude-rtl-patcher --font-only   # تطبيق خط Vazirmatn فقط، دون تغيير الاتجاه/RTL
npx claude-rtl-patcher --full        # فرض حزمة الترقيع الكاملة حتى على الإصدارات الجديدة
```

---

## 🐧 المسارات المخصصة ونظام Linux
إذا قمت بتثبيت Claude في مجلد مخصص، أو كنت تستخدم إصداراً غير رسمي على نظام Linux، قم ببساطة بتوفير مسار التثبيت الخاص بك (أو مباشرة إلى ملف `app.asar`) كـ argument:
```bash
npx claude-rtl-patcher /opt/Claude
# أو مباشرة إلى ملف asar:
npx claude-rtl-patcher /home/user/.local/share/Claude/resources/app.asar
```

---

## ⚠️ قيد معروف: تثبيتات Windows MSIX/AppX
إذا كان Claude Desktop على Windows مثبتاً كحزمة **MSIX/AppX** (يحتوي المسار على `WindowsApps`)، فإن هذه الأداة **سترفض ترقيعه**. هذا الموقع مملوك لـ `TrustedInstaller` وغير قابل للكتابة حتى كمسؤول، كما أن حزم MSIX تحمل نظام تحقق خاص بها من السلامة يمكن أن يُرجع التعديلات اليدوية بصمت على أي حال. لا يوجد حالياً حل بديل مدعوم — هذا قيد في تغليف Windows، وليس خطأً يمكن ترقيعه. راجع [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) للتفاصيل والنقاش.

---

## 🐛 تقارير المشاكل والإصلاحات

تم تطبيق الإصلاحات التالية بناءً على تقارير المجتمع في [العناوين #4–#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues):

| العنوان | المُبلّغ | المشكلة | الحل |
|---|---|---|---|
| [#4](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/4) | [amirhyz](https://github.com/amirhyz) | تسبب `plist@5` بتعطل استيراد `require('plist')` من نوع CommonJS برسالة `ERR_PACKAGE_PATH_NOT_EXPORTED`. | تم تثبيت `plist` على الإصدار المتوافق 3.x مع CommonJS وتحديث lockfile. |
| [#5](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/5) | [mkhrezaee](https://github.com/mkhrezaee) | نفس خلل `plist@5` (ESM فقط) أثّر على Windows وNode.js 22. | تم الإبقاء على الاعتماد المتوافق مع CommonJS وإضافة تغطية اختبارية. |
| [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) | [mkhrezaee](https://github.com/mkhrezaee) | تثبيتات Windows MSIX/AppX ضمن `WindowsApps` غير قابلة للكتابة ويمكن التراجع عنها بفحوصات السلامة. | تمت إضافة كشف WindowsApps، ورسالة توقف واضحة وسريعة، وتوثيق هذا القيد. |
| [#7](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/7) | [mahsakiani](https://github.com/mahsakiani) | ترقيع أحدث إصدار من macOS كان يُبطل بيانات سلامة ASAR وتوقيع الكود. | تمت إعادة حساب سلامة ASAR في `Info.plist`، وإعادة توقيع الحزمة ad-hoc، والتحقق منها، وجعل التراجع ذرّياً. |
| [#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/8) | [Ehsan-rvp](https://github.com/Ehsan-rvp) | خطأ `ERR_PACKAGE_PATH_NOT_EXPORTED` على Node.js 22/24 كان يمنع بدء التشغيل. | تمت تغطيته عبر إصلاح توافق `plist` وتحديث lockfile أعلاه. |

خيوط العناوين الأصلية لا تزال متاحة لتفاصيل إعادة الإنتاج والنقاش.

---

## ⏪ كيفية الاستعادة (Restore)
إذا أردت في أي وقت إعادة Claude إلى حالته الأصلية، فقط قم بتشغيل:
```bash
npx claude-rtl-patcher --restore
```
ستتم استعادة نسختك الاحتياطية الأصلية على الفور.

---

## 🆘 بديل: اطلب من مساعد ذكاء اصطناعي كتابة سكربت مخصص
إذا فشلت الأداة بسبب إصدار غير معروف أو أحدث من Claude Desktop، لا تقلق — تتم استعادة نسختك الاحتياطية تلقائيًا ولا يُترك شيء معطّلاً. يمكنك أيضًا أن تطلب من Claude (أو أي مساعد برمجي آخر) كتابة سكربت مخصص لإصدارك بالتحديد.

انسخ والصق هذا الطلب في Claude:

> "I use claude-rtl-patcher (https://github.com/m4tinbeigi-official/claude-rtl-patcher) to add RTL/Vazirmatn support to my local Claude Desktop install, and it failed to patch my current version. Please write a Node.js script using `@electron/asar` that extracts `app.asar`, dynamically finds and injects some CSS/JS into the `.vite/build` directory, and repacks it. On macOS it also needs to calculate the new ASAR SHA256, update the `Info.plist` file, and re-sign the app so it still launches. Please provide the complete Node.js script, and confirm with me before running anything that modifies my installed app."

*راجع السكربت الناتج بنفسك قبل تشغيله — فهو يُعدّل تثبيتك المحلي.*

---

## 🛠️ التقنيات المستخدمة
- **[Node.js](https://nodejs.org/):** المعالج الأساسي.
- **[@electron/asar](https://github.com/electron/asar):** استخراج وإعادة حزم مصادر Electron بأمان دون كسر الـ Native Modules.
- **[Inquirer](https://www.npmjs.com/package/inquirer):** قوائم الأوامر التفاعلية.
- **[Chalk](https://www.npmjs.com/package/chalk) & [Ora](https://www.npmjs.com/package/ora) & [Figlet](https://www.npmjs.com/package/figlet):** واجهة مستخدم ملونة وجميلة مع مؤشرات التحميل.
- **[Crypto]:** إعادة حساب هش سلامة ASAR الخاص بـ Electron نفسه بعد الترقيع (فحص داخلي في Electron، منفصل عن Gatekeeper الخاص بـ macOS)، وإعادة توقيع الحزمة على macOS ليقبلها Gatekeeper.

---

## 🤝 دعوة للمساهمين
نرحب بطلبات السحب (Pull Requests) من الجميع!

<a href="https://github.com/m4tinbeigi-official/claude-rtl-patcher/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=m4tinbeigi-official/claude-rtl-patcher" />
</a>

---

## ⭐ ادعم المشروع
إذا جعلت هذه الأداة تجربتك مع Claude أفضل، يرجى التفكير في إعطاء **نجمة (⭐)** لهذا المستودع في أعلى الصفحة. هذا يساعد المشروع في الوصول إلى المزيد من المستخدمين!

## 📜 الترخيص
تم النشر بموجب ترخيص **MIT** المفتوح بالكامل. أنت حر في تعديل هذا الكود وتوزيعه واستخدامه تجارياً. 🕊️
