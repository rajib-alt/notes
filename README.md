# 🧠 Nurul Amin — Obsidian Vault

> Hybrid PARA vault. Simple dashboard. Deep knowledge underneath.
> Synced to GitHub automatically every 15 minutes via Obsidian Git.

---

## 📂 Folder structure

```
00-HOME/          → Dashboard + Daily notes + Weekly reviews
01-INBOX/         → Everything lands here first. Process within 48h.
02-PROJECTS/      → One note per active project. Archive when done.
03-AREAS/         → Ongoing life areas
  Marketing/      → Limtech, BFF, content strategy
  Career/         → Applications, personal brand
  Learning/       → Courses, certifications, study notes
  Personal/       → Journal, habits, goals
  Islamic/        → Quran, duas, spiritual tracker
  Finance/        → Monthly snapshots, goals
04-RESOURCES/     → Permanent reference — never expires
  Frameworks/     → Marketing models, mental models
  Swipe-File/     → Copy inspiration by type
  Books/          → Book notes and reading list
  People/         → Lightweight contact CRM
  Tools-AI/       → n8n, AI tools, automation, Dataview guide
05-ARCHIVE/       → Completed projects and old notes
06-TEMPLATES/     → 11 Templater templates (don't edit filenames)
07-Attachments/   → PDFs, images, files
```

---

## 🏷️ Tag system

| Tag | Meaning |
|-----|---------|
| `#status/raw` | Just captured |
| `#status/processing` | Being worked on |
| `#status/done` | Complete |
| `#status/draft` | Content draft |
| `#status/studying` | Active study note |
| `#area/marketing` | Marketing area |
| `#area/career` | Career area |
| `#area/learning` | Learning area |
| `#area/islamic` | Islamic practice |
| `#work/limtech` | Limtech client work |
| `#work/bff` | BFF client work |
| `#flashcard` | Line to include in spaced repetition |

---

## ⚙️ Required plugins

Install all from Settings → Community Plugins:

| Plugin | Why |
|--------|-----|
| Dataview | Powers all the live queries in MOC and dashboard notes |
| Templater | Dynamic templates with auto-date, auto-folder |
| Tasks | Advanced task tracking with due dates |
| Periodic Notes | Auto-creates daily and weekly notes |
| Calendar | Sidebar calendar view |
| Kanban | Kanban boards inside project notes |
| Spaced Repetition | Flashcard review from `#flashcard` tags |
| Obsidian Git | Auto-commits to GitHub every 15 min |
| Homepage | Opens Dashboard on startup |
| QuickAdd | Fast capture shortcuts |
| Tag Wrangler | Rename and merge tags safely |

---

## 🚀 First-time setup

```bash
# 1. Clone this repo
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git

# 2. Open in Obsidian: Open folder as vault → select the cloned folder

# 3. Install all plugins listed above

# 4. Set Templater: template folder → 06-TEMPLATES

# 5. Set Periodic Notes: daily folder → 00-HOME/Daily, weekly → 00-HOME/Weekly

# 6. Set Homepage: default note → 00-HOME/Dashboard

# 7. Obsidian Git will auto-detect the repo — enable auto-push
```

---

## 📖 Learn Dataview

See [[04-RESOURCES/Dataview-Guide]] — beginner to advanced with real examples built for this vault.

