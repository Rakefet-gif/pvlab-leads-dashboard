# PV Lab Germany — Smart Leads Dashboard

דאשבורד לניהול לידים B2B של PV Lab Germany GmbH: מדדי KPI, ציון AI לכל ליד, ניהול סטטוסים, שלוש שפות וחיבור חי ל-Airtable.

| קובץ | תוכן |
|---|---|
| [`index.html`](index.html) | אפליקציית הדאשבורד |
| [`SPEC.md`](SPEC.md) | אפיון המערכת, כולל מבנה הטבלה ב-Airtable |
| [`Practice.md`](Practice.md) | נהלי עבודה ב-Git, ב-GitHub וב-Airtable |

## אוטומציה משלימה: קליטת לידים מ-Gmail

לידים חדשים יכולים להגיע לדאשבורד גם אוטומטית מהמייל, דרך הריפו
**[pvlab-gmail-leads-automation](https://github.com/Rakefet-gif/pvlab-gmail-leads-automation)**:

```
Gmail (מייל חדש) → Claude (ליד או לא? חילוץ פרטים) → Airtable: Leads, Status = New → הדאשבורד
                                                     ↘ Airtable: Inbox Log (חשבוניות, תמיכה, ספאם)
```

האוטומציה כותבת לאותה טבלת `Leads` ומחשבת את `Score` ואת `Value` באותה נוסחה של `calcScore` בדאשבורד,
כך שליד שהגיע מהמייל נראה בדיוק כמו ליד שהוזן ידנית. בריפו יש Blueprints לייבוא ב-**Make.com** וב-**n8n**.
