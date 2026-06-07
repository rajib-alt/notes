---
title: MOC — Books
type: moc
tags: [moc]
---

# 📖 MOC — Books

## Currently reading

```dataview
TABLE author, started
FROM "04-RESOURCES/Books"
WHERE type = "book-note" AND status = "reading"
```

## Finished

```dataview
TABLE author, rating, finished
FROM "04-RESOURCES/Books"
WHERE type = "book-note" AND status = "done"
SORT rating DESC
```

## Want to read

-
- *Atomic Habits* — James Clear
-

**New book note:** [[06-TEMPLATES/TPL-Book-Note]]
