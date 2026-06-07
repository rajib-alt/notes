---
title: MOC — People
type: moc
tags: [moc]
---

# 👥 MOC — People

## Colleagues

```dataview
LIST
FROM "04-RESOURCES/People"
WHERE type = "person-note" AND relationship = "colleague"
SORT file.name ASC
```

## Clients

```dataview
LIST
FROM "04-RESOURCES/People"
WHERE type = "person-note" AND relationship = "client"
SORT file.name ASC
```

## Mentors & contacts

```dataview
LIST
FROM "04-RESOURCES/People"
WHERE type = "person-note" AND relationship = "mentor"
SORT file.name ASC
```

**New person note:** [[06-TEMPLATES/TPL-Person-Note]]
