---
tags:
  - author
aliases:
birth_year:
nationality:
genre:
website: ""
relationship: author
type: person-note
---

# [[{{title}}]]

## 👤 Biography
* **Born:** 
* **Died:** 
* **Nationality:** 
* **Education/Background:** 

## 📚 Bibliography
*(Use wiki-links `[[Book Title]]` to link to your reading notes in your vault)*
- [[First Book Title]] (Year)
- [[Second Book Title]] (Year)

## ✍️ Style & Themes
* **Writing Style:** *(e.g., fast-paced, descriptive, stream of consciousness)*
* **Core Themes:** *(e.g., existentialism, betrayal, technology)*
* **Influences:** 

## 💡 Ideas & Connections
* **Quotes:** *"Insert notable quotes or writing philosophy here."*
* **Related Authors:** 
* **Notes:** 

---
## 📖 Works by [[{{title}}]]
```dataview
TABLE file.folder as "Folder", genre AS "Genre"
FROM "Books"
WHERE contains(author, this.file.link)
SORT file.name ASC
```
