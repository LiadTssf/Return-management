# SBA — מערכת ניהול החזרות

## מה המערכת עושה

מערכת לניהול מלא של תהליך החזרת ציוד תבניות ללקוחות חברת S.B.A.
מחליפה תקשורת מפוזרת (WhatsApp, מייל, Excel, טפסים פיזיים) במערכת מרכזית אחת —
מפתיחת תיק החזרה ועד סגירתו, כולל תיעוד, חתימות דיגיטליות, תיאום משאיות ותקשורת עם לקוחות.

## ארכיטקטורה וטכנולוגיה

| שכבה | טכנולוגיה |
|------|-----------|
| Frontend | React + Tailwind CSS + shadcn/ui (RTL עברית מלאה) |
| Backend | Supabase Edge Functions |
| Database | PostgreSQL (Supabase Cloud) |
| Storage | Supabase Storage (קבצים מוצפנים) |
| Deploy | Vercel (UI) + Supabase Cloud (backend) |
| Auth | Supabase Auth — RBAC עם 4 תפקידים |

**ארכיטקטורה:** Modular Monolith — 8 מודולים (`cases`, `customers`, `documents`, `coordination`, `notifications`, `whatsapp`, `auth`, `search`)

**סביבות:** `dev` → `staging` → `production` (deploy ל-production דורש אישור ידני)

## מבנה תיקיות

```
Return-management/
├── CLAUDE.md
├── docs/
│   ├── architecture.md       # ארכיטקטורה v1.0 — החלטות טכניות מאושרות
│   └── epics-and-stories.md  # אפיקים וסיפורי משתמש v1.2 — 7 אפיקים, 41 סיפורים
└── (קוד יתווסף כאן בהתאם לאפיקים)
```

## מצב הפרויקט

**סטטוס:** טרם התחיל פיתוח — מסמכי PRD, ארכיטקטורה ואפיקים מאושרים ומוכנים.

**סיפור נוכחי:** —

**הושלם עד כה:**
- [x] PRD v1.1 — דרישות פונקציונליות ו-NFR מאושרים
- [x] ארכיטקטורה v1.0 — כל ההחלטות הטכניות מאושרות
- [x] Epics & Stories v1.2 — 7 אפיקים, 41 סיפורים, כיסוי מלא של NFR1–NFR13
