# מחולל סטים למשחק "חמש מילים"

אפליקציית עמוד-יחיד (Static, ללא build או שרת) ליצירת סטים של מילים למשחק אימון הזיכרון "חמש מילים". האפליקציה כתובה בעברית ותומכת בכיווניות RTL.

🔗 **שימוש באפליקציה:** פתחו את `docs/index.html` בדפדפן, או גשו לגרסה המתארחת ב-GitHub Pages (אם מוגדרת עבור מאגר זה).

## מה זה עושה

- **מסך תרגול** — יוצר סט מילים אחד בכל פעם, מאפשר לסמן מילים שנזכרתם בהן, ושומר היסטוריית ציונים ב-`localStorage` (מקומית בדפדפן).
- **מסך הדפסה** — יוצר אצווה של N סטים בבת אחת, מותאם להדפסה.

כל סט נוצר באופן דטרמיניסטי ממספר "זרע" (seed) בעזרת מחולל מספרים פסאודו-אקראיים עם seed קבוע — כך שאותו זרע, כמות מילים ורמת קושי תמיד ייצרו את אותו סט מילים בדיוק, מה שמאפשר שיתוף של סט על ידי מספר יחיד.

## מבנה הפרויקט

```
docs/
├── index.html   # עיצוב, מבנה HTML וכל לוגיקת האפליקציה (JavaScript מוטבע)
└── words.js     # מאגר המילים, מקוטלג לפי קטגוריה סמנטית
```

- **`docs/words.js`** — אובייקט `bank` הממופה לפי קטגוריה (בעלי חיים, חפצים, טבע, מקומות, אוכל, אנשים/חיים, בית, שונות). כל מילה היא `{w: "<מילה>", j: 0|1}`, כאשר `j:1` מסמן מילה "עסיסית" (חיה/קונקרטית/ניתנת לדימוי) ו-`j:0` מילה נייטרלית.
- **`docs/index.html`** — כל השאר: עיצוב (CSS), מבנה (HTML) ולוגיקה (JavaScript) בקובץ אחד.

## פיתוח

אין כלי build או בדיקות. לפיתוח, פתחו את `docs/index.html` ישירות בדפדפן (או הגישו את התיקייה בעזרת שרת קבצים סטטי כלשהו) ורעננו לאחר כל שינוי.

## רישיון

טרם הוגדר רישיון לפרויקט זה.

---

# Five Words — Memory Game Set Generator

A single-page, static Hebrew (RTL) web app that generates word sets for "חמש מילים" (Five Words), a memory-training game. There is no build system, package manager, or server — it's just `index.html` and `words.js`, served from the `docs/` folder.

🔗 **Using the app:** open `docs/index.html` directly in a browser, or visit the GitHub Pages–hosted version (if enabled for this repository).

## What it does

- **Practice screen** — generates one word set at a time, lets you click the words you remembered, and tracks a scoring history persisted to `localStorage` in the browser.
- **Worksheets screen** (דפי תרגול) — generates a batch of N sets at once, styled for printing.

Word sets are generated deterministically from an integer seed via a seeded pseudo-random number generator, so the same `(seed, count, level)` always reproduces the exact same words — this is what makes a set reproducible and shareable via a single number.

## Project structure

```
docs/
├── index.html   # styles, markup, and all app logic (inline JavaScript)
└── words.js     # the word bank, categorized by semantic category
```

- **`docs/words.js`** — defines the word bank (`bank`), a plain object keyed by semantic category (animals, objects, nature, places, food, people/life, household, misc). Each word is `{w: "<hebrew word>", j: 0|1}`, where `j:1` marks a "juicy" (vivid/concrete/imageable) word and `j:0` a neutral one.
- **`docs/index.html`** — everything else: styles, markup, and all app logic in one file.

### Set generation algorithm

1. Shuffle categories with the seeded RNG and pick one word per category (repeating categories if the requested count exceeds the number of categories).
2. Balance juiciness — nudge the mix of juicy vs. neutral words toward a target ratio that depends on difficulty (easy skews juicy/vivid, hard skews neutral).
3. Fix duplicate letters — the final, authoritative pass: guarantees no two words share a first letter and no word repeats, swapping in same-category alternatives.

### History / persistence

Practice-mode results are stored in `localStorage` under the key `fiveWordsHistory` (capped at 200 entries, oldest dropped first), keyed by a generated `historyId` and updated in place as you click words.

## Development

There is no build or test tooling. To develop, open `docs/index.html` directly in a browser (or serve the directory with any static file server) and reload after edits.

## Conventions

- All UI text is in Hebrew; the document is `dir="rtl"`.
- No frameworks or dependencies beyond a Google Fonts stylesheet.
- Theming is done via CSS custom properties on `:root`, with a dark variant under `prefers-color-scheme: dark` (overridable via `data-theme="dark"`/`"light"`).

## License

No license has been set for this project yet.
