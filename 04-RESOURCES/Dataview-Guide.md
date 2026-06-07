---
title: Dataview — Learn by Doing
type: learning-note
tags: [learning, tools, dataview]
---

# 🔍 Dataview — Learn by Doing

> Dataview turns your vault into a queryable database.
> Every note's frontmatter (the `---` block at the top) becomes data you can query.
> Think of it like Excel — but for your notes.

---

## 📐 How it works — the mental model

```
Your note's frontmatter    →    Dataview sees it as a table row
type: book-note            →    column "type" = "book-note"
status: reading            →    column "status" = "reading"
rating: 4                  →    column "rating" = 4
```

You write a query inside a code block tagged `dataview`.
Dataview reads your notes and returns matching results live.

---

## 🧱 The 4 building blocks

Every Dataview query has this structure:

```
WHAT to show    →   LIST / TABLE / TASK / CALENDAR
WHERE to look   →   FROM "folder" or FROM #tag
FILTER results  →   WHERE condition
SORT & LIMIT    →   SORT field ASC/DESC   LIMIT 10
```

---

## 📋 Level 1 — LIST queries

The simplest query. Just shows note names as a list.

### List everything in a folder
```dataview
LIST
FROM "01-INBOX"
```

### List everything with a tag
```dataview
LIST
FROM #book
```

### List + sort by when it was created (newest first)
```dataview
LIST
FROM "01-INBOX"
SORT file.ctime DESC
```

### List + limit to 5 results
```dataview
LIST
FROM "04-RESOURCES/Books"
SORT file.mtime DESC
LIMIT 5
```

---

## 📊 Level 2 — TABLE queries

Shows a table with the columns you choose.

### Table of all projects with status and due date
```dataview
TABLE status, client, due
FROM "02-PROJECTS"
SORT due ASC
```

### Table of books with author and rating
```dataview
TABLE author, rating, finished
FROM "04-RESOURCES/Books"
WHERE type = "book-note"
SORT rating DESC
```

### Table of learning notes with provider
```dataview
TABLE course, provider, status
FROM "03-AREAS/Learning"
WHERE type = "learning-note"
```

### Rename a column header with AS
```dataview
TABLE status AS "Progress", due AS "Due Date"
FROM "02-PROJECTS"
```

---

## 🔍 Level 3 — WHERE filters

`WHERE` is how you narrow results. It's just a condition that's true or false.

### Only show active projects
```dataview
TABLE client, due
FROM "02-PROJECTS"
WHERE status = "active"
```

### Only show books you've finished
```dataview
TABLE author, rating
FROM "04-RESOURCES/Books"
WHERE status = "done"
```

### Only show notes modified in the last 7 days
```dataview
LIST
FROM ""
WHERE file.mtime >= date(today) - dur(7 days)
SORT file.mtime DESC
```

### Notes that contain a specific tag
```dataview
LIST
FROM ""
WHERE contains(tags, "status/processing")
```

### Multiple conditions with AND
```dataview
TABLE author, rating
FROM "04-RESOURCES/Books"
WHERE status = "done" AND rating >= 4
```

### Multiple conditions with OR
```dataview
LIST
FROM ""
WHERE contains(tags, "status/raw") OR contains(tags, "status/processing")
```

---

## ✅ Level 4 — TASK queries

Finds all `- [ ]` checkboxes across your vault.

### All incomplete tasks in your projects folder
```dataview
TASK
FROM "02-PROJECTS"
WHERE !completed
```

### All completed tasks
```dataview
TASK
FROM "02-PROJECTS"
WHERE completed
```

---

## 🗓️ Level 5 — CALENDAR queries

Shows notes on a calendar by date field.

### Calendar of all daily notes
```dataview
CALENDAR file.ctime
FROM "00-HOME/Daily"
```

### Calendar of project due dates
```dataview
CALENDAR due
FROM "02-PROJECTS"
WHERE due
```

---

## 🧮 Useful built-in fields (always available on every note)

| Field | What it is |
|-------|-----------|
| `file.name` | Note filename without extension |
| `file.path` | Full path |
| `file.ctime` | Date created |
| `file.mtime` | Date last modified |
| `file.size` | File size in bytes |
| `file.tags` | All tags in the note |
| `file.inlinks` | Notes that link TO this note |
| `file.outlinks` | Notes this note links TO |
| `file.day` | Date from filename (for daily notes like `2025-01-15`) |

---

## 🧪 Real examples built for this vault

### Dashboard — show what's in Inbox
```dataview
LIST
FROM "01-INBOX"
SORT file.ctime DESC
LIMIT 8
```

### Dashboard — active projects
```dataview
TABLE status, client, due
FROM "02-PROJECTS"
WHERE status = "active"
SORT due ASC
```

### Learning MOC — all study notes
```dataview
TABLE course, provider, status
FROM "03-AREAS/Learning"
WHERE type = "learning-note"
SORT file.mtime DESC
```

### Books MOC — currently reading
```dataview
TABLE author, started
FROM "04-RESOURCES/Books"
WHERE type = "book-note" AND status = "reading"
```

### People MOC — all clients
```dataview
LIST
FROM "04-RESOURCES/People"
WHERE type = "person-note" AND relationship = "client"
SORT file.name ASC
```

### Show all notes tagged #flashcard
```dataview
LIST
FROM ""
WHERE contains(tags, "flashcard")
```

### Notes modified today
```dataview
LIST
FROM ""
WHERE file.mday = date(today)
SORT file.mtime DESC
```

---

## ⚡ Quick reference — syntax cheat sheet

```
LIST                          → bullet list of note names
TABLE col1, col2, col3        → table with chosen columns
TASK                          → checkboxes
CALENDAR date-field           → calendar view

FROM "folder/path"            → look in a folder
FROM #tagname                 → look for a tag
FROM ""                       → search entire vault

WHERE field = "value"         → exact match
WHERE field != "value"        → not equal
WHERE field >= 4              → number comparison
WHERE contains(tags, "x")     → tag contains
WHERE file.mtime >= date(today) - dur(7 days)  → date math

SORT field ASC                → ascending (A→Z, old→new)
SORT field DESC               → descending (Z→A, new→old)
LIMIT 10                      → cap at 10 results

AS "Label"                    → rename a column
```

---

## 🚀 5 exercises to try right now

1. **Exercise 1:** Open your Dashboard. Look at the Inbox query. Change `LIMIT 8` to `LIMIT 5`. Save. Watch it update.

2. **Exercise 2:** Create a note in `04-RESOURCES/Books` with `type: book-note`, `author: James Clear`, `status: reading`. Then open `MOC-Books` — it should appear in the table automatically.

3. **Exercise 3:** Add `status: active` and `client: Limtech` to a project note. Open `MOC-Projects` — it should appear in the active table.

4. **Exercise 4:** Add `#flashcard` to a line in any learning note. Then paste this query anywhere:
   ```dataview
   LIST
   FROM ""
   WHERE contains(tags, "flashcard")
   ```
   
5. **Exercise 5:** Paste this in any note and watch it count your notes:
   ```dataview
   TABLE length(rows) AS "Total notes"
   FROM ""
   GROUP BY true
   ```

---

## 🧠 The one thing to remember

> **Garbage in, garbage out.**
> Dataview only knows what's in your frontmatter.
> The more consistently you fill in `type`, `status`, `date`, `tags` — the more powerful your queries become.
> Start with just `type` and `status`. That's enough for 80% of useful queries.

---

*Part of [[04-RESOURCES/Tools-AI/MOC-Tools-AI]]*
