# מדריך לבחירת מילים למשחק "חמש מילים"

מסמך זה מרכז את הכללים לבחירת מילים חדשות עבור `docs/words.js`, ומבוסס על שילוב של:

1. **מבחן חמש המילים (Five Words Test / Test des cinq mots)** — כלי סינון קליני לזיכרון אפיזודי מילולי שפותח ב-2002 על ידי פרופ' ברונו דובואה (Bruno Dubois) לאבחון מוקדם של מחלת אלצהיימר. המבחן מבוסס על **רמיזה סמנטית** (semantic cueing): כל מילה משויכת לקטגוריה סמנטית ייחודית, כדי להבטיח קידוד עמוק ולאפשר להבחין בין כשל בקידוד לכשל בשליפה.
2. **מחקר פסיכולינגוויסטי על זיכרון מילים** — עשרות שנות מחקר קוגניטיבי על מה הופך רשימת מילים לקלה/קשה לזכירה (ר' "מקורות" בסוף המסמך).

כללי בחירת המילים הקיימים ב-`buildSet` (index.html) — התאמת "עסיסיות" (`j`), מניעת אות פתיחה כפולה, וקטגוריות סמנטיות נפרדות — **כבר מיישמים** חלק ניכר מהעקרונות למטה. מטרת המסמך היא להסביר את הבסיס המחקרי שלהם, ולתת כללים ברורים למי שמוסיף/עורך מילים ב-`words.js`.

## עקרונות ליבה

### 1. קונקרטיות ודימוי חזותי (concreteness / imageability) → שדה `j`

מילים קונקרטיות שמעוררות דימוי חזותי (כלב, פרח, מטריה) נזכרות טוב משמעותית ממילים מופשטות (רעיון, אמת, טובה) — זהו אחד הממצאים החזקים והנשחזרים ביותר בחקר הזיכרון. לפי **תיאוריית הקידוד הכפול** של פאיביו (Paivio, Dual Coding Theory), מילה קונקרטית מקודדת גם ערוץ מילולי וגם ערוץ דימיוני-חזותי, בעוד מילה מופשטת נסמכת על הערוץ המילולי בלבד — ומכאן יתרון הזיכרון (נחקר גם כ-"picture superiority effect").

**כלל**: `j:1` = מילה קונקרטית/מוחשית שמעוררת דימוי מיידי וברור (חיה מסוימת, כלי מוכר, מאכל). `j:0` = מילה עדיין ברת-דימוי אך פחות "עסיסית" — פחות ספציפית או פחות רגשית (למשל "כיסא" לעומת "כתר", "דג" לעומת "כריש"). **הימנעו** ממילים מופשטות לגמרי (רגש מופשט, מושג פילוסופי, איכות) — הן לא מתאימות למאגר הזה כלל, גם לא כ-`j:0`, כי הן פוגעות בקלות הדימוי שהמשחק מבוסס עליה.

### 2. שכיחות וגיל רכישה (word frequency / age of acquisition) → מילים יומיומיות בלבד

מילים בעלות שכיחות גבוהה בשפה נזכרות טוב יותר ונשלפות מהר יותר ממילים נדירות; מילים שנרכשות מוקדם בחיים (age of acquisition מוקדם) מעובדות ביעילות רבה יותר מבחינה קוגניטיבית. מכיוון שהמשחק מיועד לטווח רחב של גילאים ורמות השכלה (כולל שימוש אפשרי כתרגול זיכרון למבוגרים), מילה נדירה, מקצועית, ארכאית או שאולה משפה זרה שאינה מוטמעת בעברית היומיומית פוגעת בהוגנות התרגיל — קושי לזכור אותה נובע מאי-היכרות ולא מבדיקת הזיכרון עצמה.

**כלל**: הוסיפו רק מילים נפוצות ובסיסיות שילד דובר עברית ברמת בית ספר יסודי כבר מכיר. הימנעו ממילים מקצועיות/טכניות, ארכאיות, סלנג חולף, או מילים שאולות לא-מותמעות.

### 3. אורך מילה (word length effect)

רשימות של מילים קצרות נזכרות טוב יותר מרשימות של מילים ארוכות — הסבר קלאסי מייחס זאת לזמן הנדרש ל"חזרה מילולית" (verbal rehearsal) בזיכרון עבודה (Baddeley et al.), כך שמילים קצרות "נכנסות" יותר פעמים ליחידת זמן קבועה.

**כלל**: העדיפו מילים בנות הברה-שתיים (2–4 אותיות שורש, מילה אחת ללא צירוף סמיכות ארוך). הימנעו ממילים מורכבות/ארוכות באופן קיצוני (איצטדיון, פטרוזיליה) אלא אם אין חלופה קצרה יותר לאותה קטגוריה — ואז ודאו שיש להן ניקוד `j` גבוה מספיק כדי לפצות (מילה ארוכה אך מאוד קונקרטית עדיין יכולה לתפקד היטב).

### 4. ארגון סמנטי ומניעת "ניצנוץ" בין מילים (semantic clustering) → קטגוריה אחת לכל מילה בסט

בוספילד (Bousfield, 1953) ומחקרי המשך הראו שכאשר רשימת מילים מכילה כמה מילים מאותה קטגוריה סמנטית, הנבדקים נוטים "לקבץ" (cluster) אותן זו לצד זו בשליפה — תופעה שמשפרת זכירה אך גם **מטשטשת את הבדיקה**: קל להיזכר ב"כלב" כי "חתול" כבר עלה, לא כי המילה עצמה קודדה טוב. מבחן חמש המילים הקליני בנוי סביב עיקרון דומה בכיוון ההפוך: כל מילה מקבלת קטגוריה/רמז ייחודי משלה כדי לבודד את הקידוד של כל פריט.

זהו הבסיס לכך ש-`buildSet` בוחר **מילה אחת בלבד לכל קטגוריה** בכל סט (ראו שלב 1 באלגוריתם, CLAUDE.md). עקרון זה כבר ממומש באלגוריתם ואינו דורש פעולה בעת הוספת מילים — אך **כן** משפיע על איך למיין מילה חדשה: אם מילה חדשה מתאימה לכמה קטגוריות בו-זמנית (למשל "נמר" — גם `animals` וגם קונוטציה של "מקום מסוכן"), שבצו אותה בקטגוריה שהכי ממצה את המשמעות המיידית שלה, כדי לא ליצור חפיפה סמויה עם קטגוריה אחרת.

**כלל**: אל תוסיפו לאותה קטגוריה שתי מילים כמעט-נרדפות/קרובות מדי מבחינה סמנטית (לדוגמה "ים" ו"אוקיינוס" תחת `nature`) — זה לא פוגע באלגוריתם (רק מילה אחת נבחרת לכל קטגוריה), אבל מקטין את גיוון הבחירות האפשריות בפועל.

### 5. דמיון פונולוגי/אורתוגרפי (phonological similarity effect) → מניעת אות פתיחה כפולה

מחקר קלאסי (Conrad & Hull, 1964 ואילך) הראה שרשימות של פריטים דומים-צליל (כמו האותיות B, C, D, V) נזכרות גרוע יותר מרשימות של פריטים שונים-צליל — הדמיון הפונולוגי יוצר בלבול בזמן השליפה/הסידור. `fixDuplicateLetters` ב-index.html מיישם עיקרון מקביל ברמת המילה: הבטחת אות פתיחה שונה לכל מילה בסט, שמקטינה בלבול פונטי/חזותי מוקדם בשליפה (וגם מונעת רמזים מקריים — "אני זוכר שזה התחיל ב-מ'" הופך לרמז חד-משמעי כשרק מילה אחת בסט מתחילה ב-מ').

**כלל**: אין דרישה מיוחדת בעת *הוספת* מילה בודדת ל-`words.js` (האלגוריתם דואג לכך בזמן ריצה), אבל **הימנעו מלדלל אות פתיחה מסוימת יתר על המידה** בקטגוריה אחת — אם רוב מילות `nature` מתחילות ב-מ' (מדבר, מפל, מערה, מעיין...), האלגוריתם עלול להתקשות למצוא תחליפים בזמן `fixDuplicateLetters` וייאלץ לדלג על מילים טובות. שאפו לפיזור אותיות פתיחה מגוון בתוך כל קטגוריה.

### 6. עוררות ועומק רגשי (emotional valence / arousal) — במידה, ובזהירות

מילים בעלות עוררות רגשית גבוהה (חיובית או שלילית) נזכרות טוב יותר ממילים נייטרליות — נמצא קשר בצורת U בין ולנס לזכירה (גם מילים "טובות מאוד" וגם "רעות מאוד" נזכרות טוב יותר מנייטרליות), ואפקט נפרד וליניארי לעוררות (arousal) עצמה. זה תומך בכך שמילים עם "עסיסיות" רגשית (חתונה, מסיבה) מקבלות `j:1` בצדק.

**אזהרה**: מאגר `people_life` כולל כבר כמה מילים בעלות עוצמה רגשית שלילית (לוויה, גירושין, קבר). עוררות רגשית שלילית חזקה מדי עלולה **להסיח את הדעת** מהמשימה עצמה (rehearsal מוחלף בתגובה רגשית) ואף לגרום אי-נוחות למשתתפים מבוגרים/פגיעים שהמשחק עשוי לשמש עבורם ככלי תרגול. **כלל**: הוסיפו מילים עם עוררות רגשית שלילית חזקה במשורה, והימנעו מנושאים טראומטיים במיוחד (מוות אלים, מחלה קשה, אסון). עדיפות למילים עם ולנס חיובי-קונקרטי (חתונה, מתנה, חיבוק) על פני שליליות קיצונית.

### 7. חד-משמעות (avoid ambiguity/homographs)

מילה בעלת כמה משמעויות נפרדות (הומוגרף — "עין" כאיבר לעומת מעיין מים; "רגל" כאיבר לעומת חג) עלולה לגרום לבלבול בקידוד: הדימוי הראשוני עלול להיות שונה מהמשמעות שבה השתמשה הבודקת/הבודק. עיקרון זה נגזר ישירות מדרישת הרמיזה הסמנטית החד-משמעית של מבחן חמש המילים המקורי — כל מילה נבחרת יחד עם רמז קטגורי אחד וברור.

**כלל**: העדיפו את המשמעות הנפוצה והחד-משמעית ביותר של מילה. אם למילה שתי משמעויות שכיחות במידה דומה, ודאו שהקטגוריה שבה היא ממוקמת מנחה חד-משמעית לפירוש הנכון (למשל "עין" תחת `misc`/גוף, לא תחת `nature`).

### 8. אורך הסט (list length effect)

ככל שרשימה ארוכה יותר, אחוז המילים הנזכרות יורד, ומוקד ה"פרימסי-רסנסי" (primacy/recency — נטייה לזכור טוב יותר את תחילת וסוף הרשימה, ולשכוח את האמצע) בולט יותר ברשימות ארוכות. זה כבר מיושם באפליקציה דרך פרמטר `count` ורמת קושי (`level`), ולא נוגע ישירות לבחירת מילים בודדות — אך רלוונטי אם בעתיד תתווסף אפשרות ליצור סטים ארוכים במיוחד: יש לצפות לירידה לא-ליניארית בקלות הזכירה, לא רק ירידה פרופורציונלית.

### 9. עמימות ניקוד — הומוגרפים בכתיב חסר (unpointed Hebrew ambiguity) ⚠️ ייחודי לעברית

האפליקציה מציגה טקסט עברי **ללא ניקוד**. עברית בכתיב חסר-ניקוד עמומה מטבעה: אותו רצף אותיות יכול לייצג שתי מילים שונות לגמרי בתלות בניקוד החסר — למשל "שם" (shem, שם פרטי) מול "שָם" (sham, מילת מקום — "שם" = there); "מלון" (malon, בית מלון) מול "מלון" (melon, פרי המלון); "זר" (zar, זָר/מוזר) מול "זֵר" (zer, זר פרחים). קורא שנתקל במילה כזו עלול לדמיין את המשמעות ה"לא נכונה" בזמן הקידוד — כשל תואם-עיקרון לבעיית ההומוגרפים הרגילה (עיקרון 7), אך חמור יותר כי הוא **נובע ישירות מהיעדר ניקוד באפליקציה עצמה**, לא רק מריבוי-משמעות כללי של המילה.

**כלל**: בדקו כל מילה מועמדת מול הכתיב חסר-הניקוד שלה בלבד (כפי שתוצג במשחק) — לא מול הצורה המנוקדת שבה חשבתם עליה. אם יש לרצף האותיות קריאה חלופית שכיחה באותה מידה או יותר, אל תוסיפו את המילה, או בחרו ניסוח/מילה חד-משמעית יותר (למשל "בית מלון" עדיף על "מלון" הסתמי אם יש חשש לבלבול עם פרי המלון; לרוב עדיף פשוט לדלג על המילה ולבחור חלופה נקייה מעמימות).

### 10. בולטות יחסית בתוך הסט (isolation / von Restorff effect)

אפקט פון רסטורף (von Restorff, 1933) מראה שפריט שבולט ביחס לשאר הפריטים ברשימה (שונה מהם בסוג, במשמעות, או בתחושה) נזכר טוב יותר — לא בגלל תכונה מוחלטת שלו, אלא בגלל הניגוד לסביבתו. זהו הסבר חלקי לכך שבחירת מילה אחת מכל קטגוריה (עיקרון 4) לא רק מונעת "ניצנוץ" סמנטי אלא גם **מגבירה זכירה**: כל מילה בסט בולטת ביחס לשכנותיה כי היא מגיע מעולם תוכן שונה.

**כלל**: זהו עוד נימוק (ולא כלל פעולה נוסף) לשמור על גיוון אמיתי בין הקטגוריות — קטגוריה שמכילה בעיקר מילים שקל להתבלבל איתן עם קטגוריה אחרת (למשל `household` ו-`objects` חופפים מושגית בחלקם) מַקהה את אפקט הבולטות הזה. במידת האפשר, ודאו שהדוגמאות הטיפוסיות בכל קטגוריה שונות באופן ברור מדוגמאות טיפוסיות בקטגוריות אחרות.

### 11. דמיון חזותי בין אותיות עבריות ⚠️ ייחודי לעברית

מעבר לדמיון פונולוגי (עיקרון 5), לעברית יש זוגות אותיות שדומות מאוד ויזואלית ועלולות להתבלבל בקריאה מהירה או בגופנים מסוימים: ד/ר, ב/כ (ובכתיב סופי כ/ך), ו/ז/נ, ה/ח/ת, ם/ס. מילה שמתחילה באות שקל להתבלבל בה עם אות אחרת שכבר מופיעה בסט (למשל "דג" ו"רדיו" — ד' מול ר') עלולה לפגוע באותה מטרה ש-`fixDuplicateLetters` נועד להשיג, גם אם טכנית מדובר באותיות פתיחה "שונות".

**כלל**: כשמוסיפים מילים לקטגוריה, שימו לב שלא כל המילים "הבולטות"/הנפוצות ביותר בקטגוריה מתחילות באותיות מהזוגות הדומים הנ"ל — כדי לתת לאלגוריתם מספיק אותיות פתיחה *ויזואלית מובחנות* לבחור מהן, לא רק טכנית שונות.

### 12. איזון מאגר הקטגוריות (parallel-forms / item-pool balance)

מכיוון שכל סט נוצר מ-seed מספרי (ר' README/CLAUDE.md), שני seeds שונים באותה רמת קושי אמורים לייצר סטים **בקושי דומה** — עיקרון מוכר בפסיכומטריקה כ"טפסים מקבילים" (parallel forms): כדי ששני מבחנים ייחשבו שווי-ערך, מאגר הפריטים שמהם הם נדגמים צריך להיות מאוזן בהיקפו ובמאפייניו הסטטיסטיים (קושי, יחס עסיסי/נייטרלי וכו'). אם קטגוריה אחת קטנה משמעותית מהאחרות, או שיחס `j:1`/`j:0` בה שונה בהרבה משאר הקטגוריות, סטים שדוגמים ממנה בכבדות ייצאו קלים/קשים יותר בעקביות מסטים אחרים — פוגע בהשוואתיות בין הרצות (כולל ברמת הביצוע ב"היסטוריה" שנשמרת ב-`localStorage`).

**כלל**: שאפו לשמור על **גודל דומה** בין הקטגוריות (המאגר הנוכחי נע סביב 60–65 מילים לקטגוריה — המשיכו את הטווח הזה) וכן על **יחס `j:1`/`j:0` דומה** בין קטגוריות, כדי שרמת הקושי בפועל תהיה עקבית בין קטגוריות ובין הרצות שונות של אותה רמה (`easy`/`hard`).

## רשימת בדיקה מהירה להוספת מילה חדשה

לפני הוספת מילה ל-`words.js`, ודאו:

- [ ] **מוכרת**: מילה יומיומית שילד ברמת בית ספר יסודי מכיר (לא מקצועית/ארכאית/סלנג).
- [ ] **קונקרטית**: ניתן לצייר/לדמיין אותה מיידית. אין מילים מופשטות.
- [ ] **קצרה יחסית**: עדיפות למילים קצרות; מילה ארוכה מוצדקת רק אם היא מאוד קונקרטית/`j:1`.
- [ ] **חד-משמעית**: המשמעות הראשונה שעולה בראש היא זו שהקטגוריה משקפת.
- [ ] **מדורגת נכון**: `j:1` רק אם היא באמת מעוררת דימוי חי וברור; אחרת `j:0`.
- [ ] **לא כפילות סמנטית** למילה קיימת כבר באותה קטגוריה (מילים נרדפות/קרובות מדי).
- [ ] **פיזור אותיות פתיחה**: אין דילול יתר של אות פתיחה מסוימת בקטגוריה (כולל אותיות דומות ויזואלית: ד/ר, ב/כ, ו/ז/נ, ה/ח/ת).
- [ ] **רגישות רגשית**: אם המילה טעונה שלילית, בדקו שהיא לא קיצונית/טראומטית מדי לקהל היעד.
- [ ] **נקייה מעמימות ניקוד**: בדקו את המילה בכתיב חסר-ניקוד (כפי שתוצג במשחק) — אין קריאה חלופית שכיחה באותה מידה.
- [ ] **לא פוגעת באיזון הקטגוריה**: הוספת המילה לא הופכת את גודל הקטגוריה או את יחס `j:1`/`j:0` בה לחריג ביחס לשאר הקטגוריות.

## מקורות

- Dubois, B. et al. (2002). "The 5 words": a simple and sensitive test for the diagnosis of Alzheimer's disease. — [PubMed](https://pubmed.ncbi.nlm.nih.gov/12467149/)
- Mormont, E., Jamart, J., & Robaye, L. (2012). Validity of the Five-Word Test for the Evaluation of Verbal Episodic Memory and Dementia in a Memory Clinic Setting. — [SAGE Journals](https://journals.sagepub.com/doi/abs/10.1177/0891988712445088)
- Cerbone, B. et al. Translation, Adaptation and Validation of the Five-Word Test (Test Delle 5 Parole) in an Italian Sample. — [PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9032514/)
- Paivio, A. — Dual Coding Theory; concreteness effect overview. — [Picture superiority effect (Wikipedia)](https://en.wikipedia.org/wiki/Picture_superiority_effect), [Dual coding theory and education (Clark & Paivio)](https://nschwartz.yourweb.csuchico.edu/Clark%20&%20Paivio.pdf)
- Concrete vs Abstract Words — What do you Recall Better? A Study on Dual Coding Theory. — [PeerJ Preprint](https://peerj.com/preprints/2719.pdf)
- Conrad, R., & Hull, A. J. (1964) and follow-up work on the phonological similarity effect in serial recall. — [Wiley/BJP overview](https://bpspsychub.onlinelibrary.wiley.com/doi/full/10.1111/bjop.12575), [PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9796538/)
- Bousfield, W. A. (1953). The occurrence of clustering in the recall of randomly arranged associates; and follow-up work on semantic clustering in free recall. — [ResearchGate](https://www.researchgate.net/publication/232510027_Clustering_and_organization_in_free_recall), [Interpreting semantic clustering effects in free recall (Taylor & Francis)](https://www.tandfonline.com/doi/full/10.1080/09658211.2012.683010)
- Word frequency effect in free recall — overview and mechanisms. — [Wikipedia](https://en.wikipedia.org/wiki/Word_frequency_effect), [Computational Memory Lab](https://memory.psych.upenn.edu/files/pubs/LohnKaha12.pdf)
- Baddeley, A., Thomson, N., & Buchanan, M. — word length effect in working memory. — [ScienceDirect overview](https://www.sciencedirect.com/topics/psychology/word-length-effect), [Word length effect in free recall (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4196586/)
- Age of acquisition effects on memory — re-assessment across recall/recognition tasks. — [Springer](https://link.springer.com/article/10.3758/s13421-021-01137-6)
- Serial position effect, primacy/recency, and the list length effect. — [SimplyPsychology](https://www.simplypsychology.org/primacy-recency.html), [A recency-based account of the list length effect (PubMed)](https://pubmed.ncbi.nlm.nih.gov/12450092/)
- Emotional valence and arousal effects on word memory. — [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0001691824001264), [Two routes to emotional memory (PNAS)](https://www.pnas.org/doi/10.1073/pnas.0306408101)
- Ktiv haser (כתיב חסר) — unpointed Hebrew spelling and its inherent reading ambiguity (heteronyms such as שער/שֵׂער, מלון/מָלוֹן, זר/זֵר). — [Wikipedia: Ktiv hasar niqqud](https://en.wikipedia.org/wiki/Ktiv_hasar_niqqud), [Wikipedia: Niqqud](https://en.wikipedia.org/wiki/Niqqud)
- Von Restorff, H. (1933) and follow-up work on the isolation/distinctiveness effect in memory. — [Wikipedia](https://en.wikipedia.org/wiki/Von_Restorff_effect), [Revisiting von Restorff's early isolation effect (Springer)](https://link.springer.com/article/10.3758/s13421-016-0651-6)
- Parallel forms reliability and item-pool balancing in psychometric test construction. — [Sage Research Methods](https://methods.sagepub.com/ency/edvol/encyc-of-research-design/chpt/parallel-forms-reliability), [Three-Element Item Selection Procedures for Multiple Forms Assembly (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5982169/)

---

# Guide: Choosing New Words for "Five Words"

This document summarizes the rules for adding new words to `docs/words.js`, grounded in two sources:

1. **The Five Words Test (Test des cinq mots)** — a clinical verbal episodic memory screening tool developed in 2002 by Prof. Bruno Dubois for early detection of Alzheimer's disease. It relies on **semantic cueing**: each word is paired with a unique semantic category to ensure deep encoding and to distinguish encoding failure from retrieval failure.
2. **Psycholinguistic memory research** — decades of cognitive-psychology findings on what makes a word list easy or hard to remember (see References below).

The existing rules in `buildSet` (index.html) — juiciness balancing (`j`), duplicate-first-letter prevention, and distinct semantic categories per set — **already implement** most of the principles below. This document explains their research basis and gives concrete guidance for anyone editing `words.js`.

## Core principles

### 1. Concreteness / imageability → the `j` field

Concrete, imageable words (dog, flower, umbrella) are remembered significantly better than abstract words (idea, truth, favor) — one of the most robust, replicated findings in memory research. Under Paivio's **Dual Coding Theory**, a concrete word is encoded through both a verbal and a visual/imagery channel, while an abstract word relies on the verbal channel alone, producing the memory advantage (related to the "picture superiority effect").

**Rule**: `j:1` = a concrete word that evokes an immediate, vivid image (a specific animal, a familiar tool, a food). `j:0` = still imageable but less "juicy" — less specific or less emotionally charged (e.g. "chair" vs. "throne", "fish" vs. "shark"). **Avoid** fully abstract words (abstract emotions, philosophical concepts, qualities) entirely — they don't belong in this bank even as `j:0`, since they undermine the imageability the game depends on.

### 2. Word frequency & age of acquisition → everyday words only

High-frequency words are recalled and retrieved faster and more reliably than rare words; words acquired early in life are processed more efficiently. Since the game targets a wide range of ages and literacy levels (including possible use as memory practice for older adults), a rare, technical, archaic, or unassimilated loanword undermines the fairness of the exercise — difficulty in recalling it would stem from unfamiliarity, not from testing memory itself.

**Rule**: only add common, basic words that an elementary-school-level Hebrew speaker already knows. Avoid technical/professional jargon, archaic terms, fleeting slang, or unassimilated loanwords.

### 3. Word length effect

Lists of short words are recalled better than lists of long words — classically explained by verbal rehearsal time in working memory (Baddeley et al.): short words fit more repetitions into a fixed rehearsal cycle.

**Rule**: prefer one- or two-syllable words. Avoid unusually long/compound words (e.g. "stadium", "parsley") unless there's no shorter alternative in that category — and if used, make sure their `j` rating is high enough to compensate (a long but highly concrete word can still work well).

### 4. Semantic organization / avoiding cross-item "spillover" → one word per category per set

Bousfield (1953) and follow-up work showed that when a word list contains multiple items from the same semantic category, participants tend to cluster them together at retrieval — which improves recall but also **masks the test**: "dog" becomes easy to recall because "cat" already came up, not because "dog" itself was well encoded. The clinical Five Words Test is built on the same principle in reverse: every word gets its own unique category/cue to isolate its encoding.

This is why `buildSet` picks **exactly one word per category** per set (see algorithm step 1 in CLAUDE.md) — already implemented, no action needed when adding words. It does, however, affect *which* category a new word should be filed under: if a word straddles two categories, file it under the one that best captures its immediate meaning, to avoid silent overlap with another category.

**Rule**: don't add near-synonyms to the same category (e.g. "sea" and "ocean" both under `nature`) — this doesn't break the algorithm (only one word per category is ever picked), but it reduces the effective variety of picks in practice.

### 5. Phonological/orthographic similarity effect → duplicate first-letter prevention

Classic research (Conrad & Hull, 1964, and follow-ups) showed that lists of similar-sounding items (e.g. the letters B, C, D, V) are recalled worse than dissimilar-sounding ones — similarity creates confusion at retrieval/ordering time. `fixDuplicateLetters` in index.html applies an analogous principle at the word level: guaranteeing a distinct first letter per word in a set, reducing early phonetic/visual confusion at retrieval (and avoiding accidental cue collisions — "it started with M" only helps if exactly one word in the set starts with מ).

**Rule**: no special action needed when adding a single word (the algorithm handles this at runtime), but **avoid over-concentrating** a category around one first letter — if most of `nature`'s words start with מ (מדבר, מפל, מערה, מעיין…), `fixDuplicateLetters` may struggle to find substitutes and skip good words. Aim for varied first letters within each category.

### 6. Emotional valence & arousal — in moderation, and carefully

Emotionally arousing words (positive or negative) are remembered better than neutral ones — research shows a U-shaped relationship between valence and recall (both very positive and very negative words beat neutral ones), plus a separate, linear arousal effect. This supports giving emotionally "juicy" words (wedding, party) `j:1`.

**Caution**: `people_life` already includes some strongly negative words (funeral, divorce, grave). Very strong negative arousal can **distract from the task itself** (rehearsal gets displaced by emotional reaction) and may cause discomfort for older/vulnerable users who might use this as a memory-practice tool. **Rule**: add strongly negative words sparingly, and avoid especially traumatic themes (violent death, serious illness, disaster). Prefer concrete-positive valence (wedding, gift, hug) over extreme negativity.

### 7. Avoid ambiguity/homographs

A word with multiple distinct meanings (a homograph — "עין" as body-part "eye" vs. "spring" of water; "רגל" as body-part "leg" vs. "pilgrimage/holiday") can confuse encoding: the initial image may not match the intended meaning. This principle follows directly from the clinical Five Words Test's requirement of unambiguous semantic cueing — every word is chosen together with one clear categorical cue.

**Rule**: prefer a word's most common, unambiguous meaning. If a word has two similarly common meanings, make sure the category it's filed under unambiguously points to the intended one (e.g. "eye" under a body-parts sense, not under `nature`).

### 8. List length effect

Longer lists show a lower recall percentage, and primacy/recency effects (better recall of items at the start and end of a list, worse in the middle) become more pronounced. This is already handled by the app via the `count` and `level` parameters and isn't directly relevant to choosing individual words — but is worth keeping in mind if a future feature adds unusually long sets: expect a non-linear, not just proportional, drop in recall ease.

### 9. Niqqud ambiguity — unpointed-Hebrew homographs ⚠️ Hebrew-specific

The app displays Hebrew **without niqqud** (vowel points). Unpointed Hebrew is inherently ambiguous: the same letter sequence can represent two entirely different words depending on the missing vowels — e.g. "שם" can be *shem* (a name) or *sham* (there); "מלון" can be *malon* (hotel) or *melon* (muskmelon/cantaloupe); "זר" can be *zar* (strange/a stranger) or *zer* (a bouquet). A reader hitting such a word may picture the "wrong" meaning during encoding — a special case of the homograph problem (principle 7), but more severe here because it stems **directly from the app's own lack of niqqud**, not just general word polysemy.

**Rule**: check every candidate word against its *unpointed* spelling exactly as the game will display it — not the vowelized form you had in mind. If the letter sequence has an equally or more common alternate reading, either don't add the word or pick an unambiguous alternative — usually simplest to just skip it in favor of a word free of this ambiguity.

### 10. Relative distinctiveness within a set (isolation / von Restorff effect)

The von Restorff effect (1933) shows that an item standing out from the rest of a list (different in kind, meaning, or feel) is remembered better — not because of any absolute property, but because of the contrast with its surroundings. This partly explains why picking one word per category (principle 4) doesn't just prevent semantic "spillover" but also **boosts recall**: every word in a set stands out against its neighbors because it comes from a different content domain.

**Rule**: this is additional motivation (not a new action) for keeping categories genuinely distinct — a category whose typical words are easily confused with another category's (e.g. `household` and `objects` overlap conceptually in places) dulls this distinctiveness effect. Where possible, make sure each category's typical examples read as clearly different from other categories' typical examples.

### 11. Visual similarity between Hebrew letters ⚠️ Hebrew-specific

Beyond phonological similarity (principle 5), Hebrew has letter pairs that look very similar and can be confused in quick reading or certain fonts: ד/ר (dalet/resh), ב/כ (bet/kaf, and their final forms כ/ך), ו/ז/נ (vav/zayin/nun), ה/ח/ת (he/het/tav), ם/ס (final-mem/samekh). A word starting with a letter easily confused with another word's first letter already in a set (e.g. "דג" and "רדיו" — dalet vs. resh) can undermine the same goal `fixDuplicateLetters` is meant to achieve, even though the letters are technically different.

**Rule**: when adding words to a category, watch that not all of its most common/salient words start with letters from these visually-similar pairs — so the algorithm has enough *visually distinct* first letters to choose from, not just technically distinct ones.

### 12. Category pool balance (parallel-forms / item-pool balance)

Since every set is generated from a numeric seed (see README/CLAUDE.md), two different seeds at the same difficulty level should produce sets of **comparable difficulty** — a psychometric principle known as "parallel forms": for two tests to be considered equivalent, the item pool they're drawn from needs to be balanced in size and statistical properties (difficulty, juicy/neutral ratio, etc.). If one category is much smaller than the others, or its `j:1`/`j:0` ratio diverges sharply from the rest, sets that draw heavily from it will come out consistently easier or harder than others — undermining comparability across runs (including the performance history saved in `localStorage`).

**Rule**: aim to keep categories **similar in size** (the current bank runs roughly 60–65 words per category — keep within that range) and a **similar `j:1`/`j:0` ratio** across categories, so actual difficulty stays consistent both across categories and across different runs at the same level (`easy`/`hard`).

## Quick checklist for adding a new word

- [ ] **Familiar**: an everyday word an elementary-school-level speaker already knows (not technical/archaic/slang).
- [ ] **Concrete**: can be pictured immediately. No abstract words.
- [ ] **Relatively short**: prefer short words; a long word is justified only if it's very concrete/`j:1`.
- [ ] **Unambiguous**: its first, obvious meaning is the one the category reflects.
- [ ] **Correctly rated**: `j:1` only if it truly evokes a vivid, immediate image; otherwise `j:0`.
- [ ] **No semantic duplicate** already in the same category (near-synonyms).
- [ ] **First-letter spread**: no over-concentration of one first letter within a category (including visually similar letters: ד/ר, ב/כ, ו/ז/נ, ה/ח/ת).
- [ ] **Emotional sensitivity**: if negatively charged, check it isn't extreme/traumatic for the target audience.
- [ ] **Free of niqqud ambiguity**: check the word in its unpointed spelling (as shown in the game) — no equally common alternate reading.
- [ ] **Doesn't skew category balance**: adding it doesn't make the category's size or `j:1`/`j:0` ratio an outlier relative to other categories.

## References

- Dubois, B. et al. (2002). "The 5 words": a simple and sensitive test for the diagnosis of Alzheimer's disease. — [PubMed](https://pubmed.ncbi.nlm.nih.gov/12467149/)
- Mormont, E., Jamart, J., & Robaye, L. (2012). Validity of the Five-Word Test for the Evaluation of Verbal Episodic Memory and Dementia in a Memory Clinic Setting. — [SAGE Journals](https://journals.sagepub.com/doi/abs/10.1177/0891988712445088)
- Translation, Adaptation and Validation of the Five-Word Test (Test Delle 5 Parole) in an Italian Sample. — [PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9032514/)
- Paivio, A. — Dual Coding Theory; concreteness effect overview. — [Picture superiority effect (Wikipedia)](https://en.wikipedia.org/wiki/Picture_superiority_effect), [Dual coding theory and education (Clark & Paivio)](https://nschwartz.yourweb.csuchico.edu/Clark%20&%20Paivio.pdf)
- Concrete vs Abstract Words — What do you Recall Better? A Study on Dual Coding Theory. — [PeerJ Preprint](https://peerj.com/preprints/2719.pdf)
- Conrad, R., & Hull, A. J. (1964) and follow-up work on the phonological similarity effect in serial recall. — [Wiley/BJP overview](https://bpspsychub.onlinelibrary.wiley.com/doi/full/10.1111/bjop.12575), [PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9796538/)
- Bousfield, W. A. (1953). The occurrence of clustering in the recall of randomly arranged associates; and follow-up work on semantic clustering in free recall. — [ResearchGate](https://www.researchgate.net/publication/232510027_Clustering_and_organization_in_free_recall), [Interpreting semantic clustering effects in free recall (Taylor & Francis)](https://www.tandfonline.com/doi/full/10.1080/09658211.2012.683010)
- Word frequency effect in free recall — overview and mechanisms. — [Wikipedia](https://en.wikipedia.org/wiki/Word_frequency_effect), [Computational Memory Lab](https://memory.psych.upenn.edu/files/pubs/LohnKaha12.pdf)
- Baddeley, A., Thomson, N., & Buchanan, M. — word length effect in working memory. — [ScienceDirect overview](https://www.sciencedirect.com/topics/psychology/word-length-effect), [Word length effect in free recall (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4196586/)
- Age of acquisition effects on memory — re-assessment across recall/recognition tasks. — [Springer](https://link.springer.com/article/10.3758/s13421-021-01137-6)
- Serial position effect, primacy/recency, and the list length effect. — [SimplyPsychology](https://www.simplypsychology.org/primacy-recency.html), [A recency-based account of the list length effect (PubMed)](https://pubmed.ncbi.nlm.nih.gov/12450092/)
- Emotional valence and arousal effects on word memory. — [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0001691824001264), [Two routes to emotional memory (PNAS)](https://www.pnas.org/doi/10.1073/pnas.0306408101)
- Ktiv haser (כתיב חסר) — unpointed Hebrew spelling and its inherent reading ambiguity (heteronyms such as שער/שֵׂער, מלון/מָלוֹן, זר/זֵר). — [Wikipedia: Ktiv hasar niqqud](https://en.wikipedia.org/wiki/Ktiv_hasar_niqqud), [Wikipedia: Niqqud](https://en.wikipedia.org/wiki/Niqqud)
- Von Restorff, H. (1933) and follow-up work on the isolation/distinctiveness effect in memory. — [Wikipedia](https://en.wikipedia.org/wiki/Von_Restorff_effect), [Revisiting von Restorff's early isolation effect (Springer)](https://link.springer.com/article/10.3758/s13421-016-0651-6)
- Parallel forms reliability and item-pool balancing in psychometric test construction. — [Sage Research Methods](https://methods.sagepub.com/ency/edvol/encyc-of-research-design/chpt/parallel-forms-reliability), [Three-Element Item Selection Procedures for Multiple Forms Assembly (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5982169/)
