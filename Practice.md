# Practice.md — נהלי עבודה, שמירה ועדכון ב-Git וב-GitHub

## 1. מבנה הפרויקט
* `index.html` — קובץ אפליקציית הווב הראשית (דשבורד PV Lab Germany).
* `SPEC.md` — מסמך אפיון המערכת והדרישות הפונקציונליות.
* `Practice.md` — הנחיות העבודה, השמירה והעדכון ב-GitHub.

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
