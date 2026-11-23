# Practice.md — נהלי עבודה, שמירה ועדכון ב-Git וב-GitHub

## 1. מבנה הפרויקט
* `index.html` — קובץ אפליקציית הווב הראשית (דשבורד PV Lab Germany), כולל החיבור ל-Airtable.
* `SPEC.md` — מסמך אפיון המערכת והדרישות הפונקציונליות.
* `Practice.md` — הנחיות העבודה, השמירה והעדכון ב-GitHub.
* ריפו משלים: [pvlab-gmail-leads-automation](https://github.com/Rakefet-gif/pvlab-gmail-leads-automation) — אוטומציה שיוצרת לידים בטבלת `Leads` מתוך מיילים ב-Gmail (ראו `SPEC.md` סעיף 5).

## 2. עקרונות עבודה עם Branches (ענפים)
* **ענף ראשי (`main`):** מכיל גרסה יציבה ומוכנה להצגה בלבד.
* **ענפי פיתוח (`feature/...`):** כל פיתוח חדש או עדכון מתבצע בענף צדדי וממוזג ל-`main` לאחר בדיקה.

## 3. תהליך שמירה ועדכון (Workflow)
1. יצירת ענף חדש: `git checkout -b feature/update-dashboard`
2. שמירת שינויים מקומית: `git add . && git commit -m "Update dashboard"`
3. העלאה לענן: `git push -u origin feature/update-dashboard`
4. מיזוג לענף הראשי דרך GitHub CLI: `gh pr create --fill && gh pr merge --merge`

## 4. פרסום אוטומטי ב-GitHub Pages
האתר מתארח על גבי **GitHub Pages** מתוך הענף הראשי (`main`), ומתעדכן אוטומטית בכל מיזוג.

## 5. חיבור ל-Airtable ואבטחת מפתחות
1. **הכנת הבסיס:** ב-Airtable יוצרים טבלה בשם `Leads` עם השדות שמפורטים ב-`SPEC.md` (סעיף 4).
2. **יצירת טוקן:** ב-https://airtable.com/create/tokens יוצרים Personal Access Token עם ההרשאות `data.records:read` ו-`data.records:write` בלבד, ומגבילים אותו לבסיס הזה בלבד.
3. **חיבור:** בדאשבורד לוחצים על "חיבור ל-Airtable", מזינים Base ID (מתחיל ב-`app`, מופיע בכתובת הבסיס) ואת הטוקן, ולוחצים "שמור והתחבר". האינדיקטור הופך לירוק: **Live DB Connected**.
4. **כללי אבטחה:**
   * **לעולם לא** לכתוב Base ID + טוקן בתוך `index.html`, ב-commit, ב-Issue או ב-PR. הריפו והאתר ב-GitHub Pages ציבוריים.
   * הטוקן נשמר רק ב-`localStorage` של הדפדפן שבו הוזן. כל משתמש מזין טוקן משלו בדפדפן שלו.
   * מחשב משותף: לוחצים "התנתק" בסיום העבודה כדי למחוק את הטוקן מהדפדפן.
   * אם טוקן נחשף בטעות, מבטלים אותו מיד ב-Airtable ויוצרים חדש.
5. **בדיקה לפני מיזוג:** בודקים בענף ה-feature גם מצב דמה (בלי טוקן) וגם מצב חי: טעינת רשומות, הוספת ליד ושינוי סטטוס, ומוודאים שהשינוי מופיע ב-Airtable.
