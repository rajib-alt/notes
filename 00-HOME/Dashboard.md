---
title: Dashboard
type: home
---

# 🏠 Dashboard

> Simple on the surface. Powerful underneath.

---

## 📥 Inbox — process within 48h

```dataview
LIST
FROM "01-INBOX"
SORT file.ctime DESC
LIMIT 8
```

---

## 🔴 Active projects

```dataview
TABLE status, client, due
FROM "02-PROJECTS"
WHERE status = "active"
SORT due ASC
```

---

## 🗂️ Areas

| | |
|---|---|
| [[03-AREAS/Marketing/MOC-Marketing\|📣 Marketing]] | [[03-AREAS/Career/MOC-Career\|💼 Career]] |
| [[03-AREAS/Learning/MOC-Learning\|📚 Learning]] | [[03-AREAS/Islamic/MOC-Islamic\|🕌 Islamic]] |
| [[03-AREAS/Personal/MOC-Personal\|🙋 Personal]] | [[03-AREAS/Finance/MOC-Finance\|💰 Finance]] |

---

## 🧠 Resources

| | |
|---|---|
| [[04-RESOURCES/Frameworks/MOC-Frameworks\|🧩 Frameworks]] | [[04-RESOURCES/Swipe-File/MOC-Swipe-File\|✍️ Swipe File]] |
| [[04-RESOURCES/Books/MOC-Books\|📖 Books]] | [[04-RESOURCES/People/MOC-People\|👥 People]] |
| [[04-RESOURCES/Tools-AI/MOC-Tools-AI\|🛠️ Tools & AI]] | |

---

## 📅 Recent weekly reviews

```dataview
TABLE file.mtime AS "Date"
FROM "00-HOME/Weekly"
SORT file.mtime DESC
LIMIT 3
```

---

## 🏷️ Notes needing attention

```dataview
LIST
FROM ""
WHERE contains(tags, "status/processing") OR contains(tags, "status/raw")
SORT file.mtime DESC
LIMIT 10
```
