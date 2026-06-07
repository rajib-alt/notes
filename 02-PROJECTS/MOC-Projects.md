---
title: MOC — Projects
type: moc
tags: [moc]
---

# 🗂️ MOC — Projects

One note per active project. When complete → move to [[05-ARCHIVE]].

## 🔴 Active

```dataview
TABLE client, due, status
FROM "02-PROJECTS"
WHERE type = "project" AND status = "active"
SORT due ASC
```

## ✅ Recently archived

```dataview
TABLE client, file.mtime AS "Archived"
FROM "05-ARCHIVE"
WHERE type = "project"
SORT file.mtime DESC
LIMIT 5
```

**New project:** Use template [[06-TEMPLATES/TPL-Project-Brief]]
