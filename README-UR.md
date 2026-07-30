<div align="center">
  <img src="./assets/preview.png" alt="Claude RTL Patcher Preview" width="100%">

  <h1>🌟 Claude RTL Patcher</h1>
  <p><strong>Claude Desktop ایپ میں دائیں سے بائیں (RTL) ٹیکسٹ اور خوبصورت فونٹ کے لیے بہترین خودکار پیچر۔</strong></p>
  <p>فارسی · عربی · عبرانی · اردو · پشتو · سندھی · کردی (سورانی) · دیویہی · یدیش</p>

  [![npm version](https://badge.fury.io/js/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![npm downloads](https://img.shields.io/npm/dm/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  [![GitHub stars](https://img.shields.io/github/stars/m4tinbeigi-official/claude-rtl-patcher.svg?style=social&label=Star)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/stargazers)

  ✨ *RTL Rick Sanchez نے لاگو کیا، اور Vazirmatn فونٹ Saber Rastikerdar کی یاد میں استعمال کیا گیا۔* ✨

  [🇺🇸 Read in English](./README.md) | [🇮🇷 نسخه فارسی (Persian)](./README-FA.md) | [🇸🇦 اقرأ بالعربية (Arabic)](./README-AR.md) | [🇮🇱 קרא בעברית (Hebrew)](./README-HE.md)
</div>

---

یہ ایک اوپن سورس، خودکار ٹول ہے جو مضبوط **دائیں سے بائیں (RTL)** سپورٹ اور خوبصورت **Vazirmatn** فونٹ کو براہِ راست آفیشل **Claude Desktop App** (macOS، Windows، Linux) میں شامل کرتا ہے۔

یہ فارسی، عربی، عبرانی، اردو، پشتو، سندھی، کردی (سورانی)، دیویہی اور یدیش کے لیے ٹیکسٹ الائنمنٹ کی خرابی ٹھیک کرتا ہے — تاکہ آپ Claude کے ساتھ آسانی سے بات چیت کر سکیں۔ یہ فکس یونیکوڈ کے bidi الگورتھم کی سطح پر کام کرتا ہے (`unicode-bidi: plaintext`)، ہر زبان کے لیے علیحدہ کوڈ لکھنے کی بجائے — اس لیے یہ صرف ان تین زبانوں تک محدود نہیں جن سے یہ پروجیکٹ شروع ہوا تھا۔

🎉 یہ پروجیکٹ **[سرکاری طور پر عالمی NPM رجسٹری پر شائع ہو چکا ہے](https://www.npmjs.com/package/claude-rtl-patcher)**!

> **خودکار پتہ لگانے کا موڈ:** Claude Desktop کے نئے ورژنز پہلے ہی خود بخود RTL درست طریقے سے دکھاتے ہیں۔ جب ایسا پتہ چلے تو پیچر صرف **Vazirmatn فونٹ** لگاتا ہے اور سمت/الائنمنٹ کو نہیں چھیڑتا۔ پرانے ورژنز پر (جن میں مقامی RTL نہیں ہے) مکمل پیچ (فونٹ + RTL) لاگو ہوتا ہے۔ آپ `--font-only` یا `--full` سے خود بھی موڈ چن سکتے ہیں۔

## 🚀 ایک کلک انسٹالیشن (تجویز کردہ)

آپ کو کچھ بھی دستی طور پر ڈاؤن لوڈ یا انسٹال کرنے کی ضرورت نہیں۔ بس اپنے سسٹم کا ٹرمینل (CMD / PowerShell / Mac Terminal) کھولیں اور یہ کمانڈ پیسٹ کریں:

```bash
npx claude-rtl-patcher
```

*(یہ اسکرپٹ خودکار طور پر آپ کا آپریٹنگ سسٹم اور Claude کا ورژن پتہ لگاتا ہے، بیک اپ بناتا ہے، مناسب CSS انجیکٹ کرتا ہے، اور — macOS پر — ایپ کو دوبارہ سائن اور تصدیق کرتا ہے تاکہ وہ چلتی رہے، سب کچھ چند سیکنڈز میں۔)*

مکمل ہونے کے بعد، Claude کو مکمل طور پر بند کریں (`Cmd + Q` یا `Ctrl + Q`) اور دوبارہ کھولیں۔

### اسٹینڈ اَلون انسٹالر (Node.js کی ضرورت نہیں)

ہر ریلیز کے ساتھ macOS، Windows اور Linux کے لیے خودکار طور پر ایگزیکیوٹیبل فائلیں بنتی ہیں۔ ریلیز کے بعد متعلقہ فائل ڈاؤن لوڈ کریں یا یہ کمانڈ چلائیں:

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.sh | bash

# Windows PowerShell
irm https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.ps1 | iex
```

یہ اسٹینڈ اَلون ورژن موجودہ صارف کے لیے پیچر انسٹال کرتا ہے، آپریٹنگ سسٹم اور Claude کا راستہ پتہ لگاتا ہے، بیک اپ بناتا ہے، اور وہی انٹرایکٹو پیچ کا عمل چلاتا ہے۔ Windows کے MSIX/AppX انسٹالز اب بھی سپورٹڈ نہیں ہیں کیونکہ ان کی پیکج فائلیں لکھنے کے قابل نہیں۔

### مخصوص موڈ کو زبردستی لاگو کرنا

```bash
npx claude-rtl-patcher --font-only   # صرف Vazirmatn فونٹ، سمت/RTL میں تبدیلی نہیں
npx claude-rtl-patcher --full        # نئے ورژنز پر بھی مکمل RTL + فونٹ پیچ زبردستی لگائیں
```

---

## 🐧 مخصوص راستے اور Linux

اگر آپ نے Claude کسی مخصوص فولڈر میں انسٹال کیا ہے، یا آپ Linux کا کوئی غیر رسمی ورژن استعمال کر رہے ہیں، تو بس اپنی انسٹالیشن کا راستہ (یا براہِ راست `app.asar` فائل) بطور آرگیومنٹ دیں:

```bash
npx claude-rtl-patcher /opt/Claude
# یا براہِ راست asar فائل کو:
npx claude-rtl-patcher /home/user/.local/share/Claude/resources/app.asar
```

---

## ⚠️ معلوم حد: Windows پر MSIX/AppX انسٹالز

اگر Windows پر Claude Desktop **MSIX/AppX پیکج** کے طور پر انسٹال ہے (راستے میں `WindowsApps` شامل ہو)، تو یہ ٹول **اسے پیچ کرنے سے انکار کرے گا**۔ وہ جگہ `TrustedInstaller` کی ملکیت ہے اور ایڈمن کے طور پر بھی لکھنے کے قابل نہیں، اور MSIX پیکجز کا اپنا انٹیگریٹی ویریفیکیشن سسٹم ہے جو خاموشی سے تبدیلیاں واپس کر سکتا ہے۔ فی الحال اس کا کوئی سپورٹڈ حل نہیں — یہ Windows کی پیکجنگ کی حد ہے، کوئی بگ نہیں جسے پیچ کیا جا سکے۔ تفصیلات کے لیے [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) دیکھیں۔

---

## 🐛 رپورٹ شدہ مسائل اور ان کے حل

کمیونٹی کی رپورٹس ([issues #4–#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues)) کی بنیاد پر درج ذیل اصلاحات کی گئیں:

| Issue | رپورٹ کرنے والا | مسئلہ | حل |
|---|---|---|---|
| [#4](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/4) | [amirhyz](https://github.com/amirhyz) | `plist@5` نے `require('plist')` کو `ERR_PACKAGE_PATH_NOT_EXPORTED` کے ساتھ کریش کر دیا۔ | `plist` کو CommonJS-موافق ورژن 3.x پر مقرر کیا گیا اور lockfile اپڈیٹ کی گئی۔ |
| [#5](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/5) | [mkhrezaee](https://github.com/mkhrezaee) | یہی ESM-صرف والا مسئلہ Windows اور Node.js 22 پر بھی آیا۔ | مطابقت رکھنے والی CommonJS ڈیپنڈنسی برقرار رکھی گئی اور ٹیسٹ کوریج شامل کی گئی۔ |
| [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) | [mkhrezaee](https://github.com/mkhrezaee) | Windows کے `WindowsApps` والے MSIX/AppX انسٹالز لکھنے کے قابل نہیں اور انٹیگریٹی چیک انہیں واپس کر سکتا ہے۔ | WindowsApps کی تشخیص، واضح پیغام کے ساتھ فوری روک، اور اس حد کی دستاویز شامل کی گئی۔ |
| [#7](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/7) | [mahsakiani](https://github.com/mahsakiani) | نئے macOS ورژن کو پیچ کرنے سے ASAR انٹیگریٹی اور کوڈ سائننگ خراب ہو جاتی تھی۔ | `Info.plist` کی ASAR انٹیگریٹی دوبارہ شمار کی گئی، بنڈل کو ad-hoc دوبارہ سائن اور تصدیق کیا گیا، اور rollback کو atomic بنایا گیا۔ |
| [#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/8) | [Ehsan-rvp](https://github.com/Ehsan-rvp) | Node.js 22/24 پر `ERR_PACKAGE_PATH_NOT_EXPORTED` کی وجہ سے شروع نہیں ہوتا تھا۔ | اوپر والی `plist` مطابقت اور lockfile اپڈیٹ سے حل ہوا۔ |

تفصیلات اور بحث کے لیے اصل issue threads اب بھی دستیاب ہیں۔

---

## ⏪ واپس اصل حالت پر کیسے لائیں (Restore)

اگر کبھی Claude کو اصل حالت پر واپس لانا چاہیں، تو بس یہ چلائیں:

```bash
npx claude-rtl-patcher --restore
```

آپ کا اصل بیک اپ فوری طور پر بحال ہو جائے گا۔

---

## 🆘 متبادل: کسی AI اسسٹنٹ سے مخصوص اسکرپٹ مانگیں

اگر پیچر کسی نامعلوم یا نئے Claude Desktop ورژن پر ناکام ہو جائے تو فکر نہ کریں — آپ کا بیک اپ خودکار طور پر بحال ہو جاتا ہے اور کچھ بھی خراب نہیں رہتا۔ آپ Claude (یا کوئی بھی کوڈنگ اسسٹنٹ) سے اپنے مخصوص ورژن کے لیے ایک نیا پیچ اسکرپٹ لکھنے کو بھی کہہ سکتے ہیں۔

یہ پرامپٹ کاپی کر کے پیسٹ کریں:

> "I use claude-rtl-patcher (https://github.com/m4tinbeigi-official/claude-rtl-patcher) to add RTL/Vazirmatn support to my local Claude Desktop install, and it failed to patch my current version. Please write a Node.js script using `@electron/asar` that extracts `app.asar`, injects the same CSS/JS into the `.vite/build`/`.vite/renderer` directories, and repacks it. On macOS it must calculate Electron's integrity hash from the serialized `headerString` returned by `require('@electron/asar').getRawHeader(asarPath)` (not from the whole ASAR), update `ElectronAsarIntegrity` in `Info.plist`, run `/usr/bin/xattr -cr <app-bundle>`, materialize a sanitized entitlement plist that excludes `com.apple.application-identifier`, `com.apple.developer.team-identifier`, and `keychain-access-groups`, ad-hoc sign the complete bundle with `/usr/bin/codesign --force --deep --sign - --entitlements <temporary-plist> <app-bundle>`, and verify it with `/usr/bin/codesign --verify --deep --strict --verbose=2 <app-bundle>`. If patching or signing fails, it must restore the original ASAR and `Info.plist`, recompute integrity, and re-sign and verify the rollback. Please provide the complete Node.js script, and confirm with me before running anything that modifies my installed app."

*اسکرپٹ چلانے سے پہلے خود اسے دیکھ لیں — یہ آپ کی مقامی انسٹالیشن میں تبدیلی کرتا ہے۔*

---

## 🛠️ استعمال شدہ ٹیکنالوجیز

- **[Node.js](https://nodejs.org/):** بنیادی پروسیسر۔
- **[@electron/asar](https://github.com/electron/asar):** Native Modules کو نقصان پہنچائے بغیر Electron سورسز کا محفوظ استخراج اور دوبارہ پیکجنگ۔
- **[Inquirer](https://www.npmjs.com/package/inquirer):** انٹرایکٹو CLI مینیوز۔
- **[Chalk](https://www.npmjs.com/package/chalk) اور [Ora](https://www.npmjs.com/package/ora) اور [Figlet](https://www.npmjs.com/package/figlet):** خوبصورت رنگین UI اور اسپنرز۔
- **[Crypto]:** پیچ کے بعد Electron کے اپنے ASAR انٹیگریٹی ہیش کا دوبارہ حساب (یہ Electron کا اپنا چیک ہے، macOS Gatekeeper سے الگ)، اور macOS پر بنڈل کو دوبارہ سائن کرنا تاکہ Gatekeeper اسے قبول کرے۔

---

## 🤝 تعاون کی دعوت

ہم سب کی طرف سے pull requests کا خیرمقدم کرتے ہیں!

<a href="https://github.com/m4tinbeigi-official/claude-rtl-patcher/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=m4tinbeigi-official/claude-rtl-patcher" />
</a>

---

## ⭐ پروجیکٹ کی حمایت کریں

اگر اس ٹول نے آپ کے Claude کے تجربے کو بہتر بنایا ہے، تو براہِ کرم صفحے کے اوپر اس ریپوزیٹری کو **اسٹار (⭐)** دینے پر غور کریں۔ اس سے پروجیکٹ زیادہ صارفین تک پہنچتا ہے!

## 📜 لائسنس

مکمل طور پر آزاد **MIT License** کے تحت شائع کیا گیا۔ آپ اس کوڈ میں ترمیم، تقسیم، اور تجارتی استعمال کرنے کے لیے آزاد ہیں۔ 🕊️
