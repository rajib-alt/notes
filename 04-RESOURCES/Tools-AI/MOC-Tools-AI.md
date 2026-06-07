---
title: MOC — Tools & AI
type: moc
tags: [moc]
---

# 🛠️ MOC — Tools & AI

## AI tools

| Tool | Use | Notes |
|------|-----|-------|
| Claude | Copy, strategy, vault | API |
| n8n | Automation | Self-hosted |
| Gemini | Quick lookups | API |
| OpenRouter | Free model cascade | Free tier |

## n8n workflows
- Weekend report generator (Facebook Insights CSV)
- Social data transformer
- SEO audit tool

## Analytics

| Tool | Purpose |
|------|---------|
| Facebook Insights | BFF & Limtech |
| Google Analytics | Web |
| Semrush | SEO |

## Problem-solution log

```dataview
LIST
FROM "04-RESOURCES/Tools-AI"
WHERE type = "problem-solution"
SORT file.mtime DESC
```
