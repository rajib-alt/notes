---
title: MOC — Inbox
type: moc
tags: [moc]
---

# 📥 MOC — Inbox

Everything lands here first. Process within 48 hours.

**Workflow:**
1. Capture anything here quickly
2. Once processed, move to the right folder
3. Change `status` tag from `raw` → `processing` → `done`

```dataview
LIST
FROM "01-INBOX"
WHERE file.name != "MOC-Inbox"
SORT file.ctime DESC
```
