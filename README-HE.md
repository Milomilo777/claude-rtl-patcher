<div align="center">
  <img src="./assets/preview.png" alt="Claude RTL Patcher Preview" width="100%">
  
  <h1>🌟 Claude RTL Patcher</h1>
  <p><strong>הכלי האוטומטי האולטימטיבי לתמיכה בטקסט מימין לשמאל (RTL) וטיפוגרפיה יפה באפליקציית שולחן העבודה של Claude.</strong></p>
  <p>פרסית · ערבית · עברית · אורדו · פשטו · סינדהית · כורדית (סוראנית) · דיווהית · יידיש</p>

  [![npm version](https://badge.fury.io/js/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![npm downloads](https://img.shields.io/npm/dm/claude-rtl-patcher.svg)](https://www.npmjs.com/package/claude-rtl-patcher)
  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  [![GitHub stars](https://img.shields.io/github/stars/m4tinbeigi-official/claude-rtl-patcher.svg?style=social&label=Star)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/stargazers)

  ✨ *תמיכת RTL יושמה על ידי Rick Sanchez, גופן Vazirmatn הוסף לזכרו של Saber Rastikerdar.* ✨

  [🇺🇸 Read in English](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README.md) | [🇮🇷 نسخه فارسی (Persian)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-FA.md) | [🇸🇦 اقرأ بالعربية (Arabic)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-AR.md) | [🇵🇰 اردو میں پڑھیں (Urdu)](https://github.com/m4tinbeigi-official/claude-rtl-patcher/blob/main/README-UR.md)
</div>

---

זהו כלי קוד פתוח ואוטומטי שמוסיף תמיכה מלאה וטובה בטקסט מימין לשמאל **(RTL)** ישירות לאפליקציית שולחן העבודה הרשמית של **Claude** (עבור macOS, Windows ו-Linux).

הכלי מתקן בעיות יישור טקסט עבור פרסית, ערבית, עברית, אורדו, פשטו, סינדהית, כורדית (סוראנית), דיווהית ויידיש — כדי שתוכלו לשוחח עם Claude בצורה חלקה. התיקון פועל ברמת אלגוריתם ה-bidi של יוניקוד (`unicode-bidi: plaintext`), לא בטיפול מיוחד לכל שפה בנפרד, ולכן הוא אינו מוגבל לשלוש השפות שאיתן הפרויקט התחיל.

🎉 הפרויקט הזה **[פורסם רשמית במאגר ה-NPM הגלובלי](https://www.npmjs.com/package/claude-rtl-patcher)**!

> **מצב זיהוי אוטומטי:** גרסאות חדשות יותר של Claude Desktop כבר מציגות RTL נכון מעצמן. כשזה מזוהה, המתקן מחיל **רק את גופן Vazirmatn** ולא נוגע בכיוון/יישור. בגרסאות ישנות יותר (ללא תמיכת RTL מובנית) עדיין מוחל הפאץ' המלא (גופן + RTL). ניתן גם לכפות מצב ידנית עם `--font-only` או `--full`.

## 🚀 התקנה בלחיצה אחת (מומלץ)

אין צורך להוריד או להתקין שום דבר באופן ידני. פשוט פתחו את מסוף הפקודות שלכם (CMD / PowerShell / Mac Terminal) והדביקו את פקודת הקסם הזו:

```bash
npx claude-rtl-patcher
```

*(הסקריפט כולל ממשק שורת פקודה אינטראקטיבי (CLI) שיזהה אוטומטית את מערכת ההפעלה שלכם, ייצור גיבוי, יזריק את ה-CSS, ו-ב-macOS יחתום מחדש על האפליקציה ויוודא שהיא עדיין נפתחת - הכל תוך שניות.)*

בסיום התהליך, סגרו לחלוטין את Claude (באמצעות `Cmd + Q` או `Ctrl + Q`) ופתחו אותו מחדש.

### מתקין עצמאי (ללא צורך ב-Node.js)
קבצי הרצה עבור כל גרסה נבנים אוטומטית עבור macOS, Windows ו-Linux. לאחר פרסום גרסה, הורידו את הקובץ המתאים או הריצו את פקודת ההתקנה:

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.sh | bash

# Windows PowerShell
irm https://raw.githubusercontent.com/m4tinbeigi-official/claude-rtl-patcher/main/install.ps1 | iex
```

הגרסה העצמאית מתקינה את הכלי עבור המשתמש הנוכחי, מזהה את מערכת ההפעלה ואת נתיב Claude, יוצרת גיבוי, ומפעילה את אותו תהליך תיקון אינטראקטיבי. התקנות Windows MSIX/AppX עדיין אינן נתמכות מכיוון שקבצי החבילה שלהן אינם ניתנים לכתיבה.

### כפיית מצב מסוים
```bash
npx claude-rtl-patcher --font-only   # רק גופן Vazirmatn, ללא שינוי כיוון/RTL
npx claude-rtl-patcher --full        # כפיית הפאץ' המלא גם בגרסאות חדשות
```

---

## 🐧 נתיבים מותאמים אישית ו-Linux
אם התקנתם את Claude בתיקייה מותאמת אישית, או שאתם משתמשים בגרסת Linux לא רשמית, פשוט ספקו לסקריפט את נתיב ההתקנה שלכם (או ישירות לקובץ `app.asar`) כארגומנט:
```bash
npx claude-rtl-patcher /opt/Claude
# או ישירות לקובץ asar:
npx claude-rtl-patcher /home/user/.local/share/Claude/resources/app.asar
```

---

## ⚠️ מגבלה ידועה: התקנות Windows MSIX/AppX
אם Claude Desktop ב-Windows הותקן כחבילת **MSIX/AppX** (הנתיב מכיל `WindowsApps`), הכלי **יסרב לתקן אותה**. המיקום הזה שייך ל-`TrustedInstaller` ואינו ניתן לכתיבה אפילו כמנהל מערכת, וחבילות MSIX נושאות מנגנון אימות שלמות משלהן שיכול לבטל בשקט עריכות ידניות בכל מקרה. כרגע אין פתרון עוקף נתמך — זו מגבלה של אריזת Windows, לא באג שאפשר לתקן. ראו [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) לפרטים ולדיון.

---

## 🐛 דיווחי בעיות ותיקונים

התיקונים הבאים בוצעו בעקבות דיווחי הקהילה ב-[issues #4–#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues):

| Issue | דווח על ידי | הבעיה | הפתרון |
|---|---|---|---|
| [#4](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/4) | [amirhyz](https://github.com/amirhyz) | `plist@5` גרם לקריסת ה-import של `require('plist')` (CommonJS) עם `ERR_PACKAGE_PATH_NOT_EXPORTED`. | `plist` הוצמד לגרסת 3.x התואמת ל-CommonJS, ו-lockfile עודכן. |
| [#5](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/5) | [mkhrezaee](https://github.com/mkhrezaee) | אותה תקלת `plist@5` (ESM בלבד) פגעה גם ב-Windows וב-Node.js 22. | נשמרה תלות תואמת ל-CommonJS ונוספה כיסוי בדיקות. |
| [#6](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/6) | [mkhrezaee](https://github.com/mkhrezaee) | התקנות Windows MSIX/AppX תחת `WindowsApps` אינן ניתנות לכתיבה ועלולות להתבטל על ידי בדיקות שלמות. | נוספה זיהוי WindowsApps, הודעת עצירה מהירה וברורה, ותיעוד המגבלה. |
| [#7](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/7) | [mahsakiani](https://github.com/mahsakiani) | תיקון גרסת macOS העדכנית ביותר פסל את נתוני שלמות ה-ASAR ואת חתימת הקוד. | שלמות ה-ASAR ב-`Info.plist` חושבה מחדש, החבילה נחתמה מחדש ad-hoc, אומתה, וה-rollback הפך אטומי. |
| [#8](https://github.com/m4tinbeigi-official/claude-rtl-patcher/issues/8) | [Ehsan-rvp](https://github.com/Ehsan-rvp) | שגיאת `ERR_PACKAGE_PATH_NOT_EXPORTED` ב-Node.js 22/24 מנעה הפעלה. | נפתר על ידי תיקון התאימות של `plist` ועדכון ה-lockfile שלמעלה. |

שרשורי ה-issues המקוריים עדיין זמינים לפרטי שחזור ודיון.

---

## ⏪ איך לבצע שחזור (Restore)
אם אי פעם תרצו להחזיר את Claude למצבו המקורי, פשוט הריצו:
```bash
npx claude-rtl-patcher --restore
```
הגיבוי המקורי שלכם ישוחזר באופן מיידי.

---

## 🆘 חלופה: בקשו מסייע בינה מלאכותית לכתוב סקריפט מותאם אישית
אם כלי התיקון נכשל עקב גרסה לא מוכרת או חדשה יותר של Claude Desktop, אל תדאגו — הגיבוי שלכם משוחזר אוטומטית ושום דבר לא נשאר שבור. תוכלו גם לבקש מ-Claude (או כל מסייע קידוד אחר) לכתוב סקריפט תיקון מותאם אישית לגרסה המדויקת שלכם.

העתיקו והדביקו את הפקודה הזו בתוך Claude:

> "I use claude-rtl-patcher (https://github.com/m4tinbeigi-official/claude-rtl-patcher) to add RTL/Vazirmatn support to my local Claude Desktop install, and it failed to patch my current version. Please write a Node.js script using `@electron/asar` that extracts `app.asar`, dynamically finds and injects some CSS/JS into the `.vite/build` directory, and repacks it. On macOS it also needs to calculate the new ASAR SHA256, update the `Info.plist` file, and re-sign the app so it still launches. Please provide the complete Node.js script, and confirm with me before running anything that modifies my installed app."

*בדקו בעצמכם את הסקריפט שנוצר לפני ההרצה — הוא משנה את ההתקנה המקומית שלכם.*

---

## 🛠️ טכנולוגיות בשימוש
- **[Node.js](https://nodejs.org/):** מעבד הליבה.
- **[@electron/asar](https://github.com/electron/asar):** חילוץ ואריזה מחדש בטוחים של מקורות Electron ללא שבירת רכיבי Native Modules.
- **[Inquirer](https://www.npmjs.com/package/inquirer):** תפריטי CLI אינטראקטיביים.
- **[Chalk](https://www.npmjs.com/package/chalk) & [Ora](https://www.npmjs.com/package/ora) & [Figlet](https://www.npmjs.com/package/figlet):** ממשק משתמש צבעוני ויפהפה עם אינדיקטורים נעים (Spinners).
- **[Crypto]:** חישוב מחדש של גיבוב ה-integrity הפנימי של ASAR ב-Electron לאחר הפאץ' (בדיקה פנימית של Electron עצמו, נפרדת מ-Gatekeeper של macOS), וחתימה מחדש של החבילה ב-macOS כדי ש-Gatekeeper יקבל את האפליקציה המתוקנת.

---

## 🤝 קריאה לתורמים (Contributors)
אנו מקדמים בברכה Pull Requests מכולם!

<a href="https://github.com/m4tinbeigi-official/claude-rtl-patcher/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=m4tinbeigi-official/claude-rtl-patcher" />
</a>

---

## ⭐ תמכו בפרויקט
אם כלי זה שיפר את חווית השימוש שלכם ב-Claude, אנא שקלו להעניק **כוכב (⭐)** למאגר זה בראש העמוד. זה עוזר לפרויקט להגיע ליותר משתמשים!

## 📜 רישיון
מפורסם תחת רישיון **MIT** מתירני לחלוטין. אתם חופשיים לשנות, להפיץ ולהשתמש בקוד זה באופן מסחרי. 🕊️
