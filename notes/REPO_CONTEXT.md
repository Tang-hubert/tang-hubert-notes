# REPO_CONTEXT.md - AI Schema for This Repository

> **Purpose**: This file serves as the single source of truth for understanding this repository's structure, rules, and workflows. All AI agents and collaborators should read this file first before making any changes.

---

## 📚 Repository Overview

### What This Repository Is

This is **Tang-hubert's personal tech learning journal**, a GitHub Pages website that tracks daily technical skills learned, projects worked on, and business insights gained.

### Core Philosophy

- **Chronological Records**: Daily entries capture what was learned on each date
- **Stackable Knowledge**: Long-term reusable content lives in `notes/knowledge/` folder
- **Linked References**: Daily entries reference knowledge folder for deep dives
- **Human-Readable**: Well-organized for both human review and AI understanding

---

## 🎯 Core Rules (MUST FOLLOW)

### 1. REPO_CONTEXT.md = Pure Schema Only
This file contains **ONLY rules, structure, and patterns** — no actual learning content.

### 2. Content Goes in Dedicated Folders
```
knowledge/     → Long-term, stackable, reusable notes
daily-learnings/ → Daily records, timestamps, immediate learnings
```

### 3. Daily Entries Link to Knowledge
Every daily entry should reference related knowledge folder notes when applicable.

### 4. Always Get User Permission Before Pushing
Never push to GitHub without explicit user confirmation.

### 5. Save Google AI Studio Links
Whenever user pastes a Google AI Studio link, **ALWAYS** add it to the notes (Resources section). These links contain their thinking, learning roadmap, evaluations, and research.

### 6. UPDATE README Files
Always update `notes/daily-learnings/README.md` when adding new daily entries.

### 7. USE knowledge/ Folder for Long-Term Notes
Don't forget it exists! Use `notes/knowledge/[topic]/` for stackable, reusable content that will be referenced across multiple entries.

### 8. Add New Knowledge Topics When Relevant
When creating daily entries, check if new knowledge folders should be created under `notes/knowledge/`. Update the daily entry's "Related Knowledge" section accordingly.

---

## 📁 Repository Structure

```
notes/
├── REPO_CONTEXT.md                    # THIS FILE - Schema/Rules ONLY
│
├── knowledge/                         # Long-term, stackable knowledge base
│   └── [topic]/                       # Topic folder (lowercase-with-dashes)
│       ├── README.md                  # Index for this topic
│       └── *.md                       # Detailed concept notes
│
└── daily-learnings/                  # Daily learning records
    ├── README.md                      # Master index
    └── YYYY/
        ├── YYYY.md                    # Yearly summary (ALL skills)
        └── MM/
            └── YYYY-MM-DD.md          # Daily entry
```

---

## 📋 File Naming Conventions

| Type | Format | Example |
|------|--------|---------|
| Daily Entry | `YYYY-MM-DD.md` | `2026-03-17.md` |
| Yearly Summary | `YYYY.md` | `2026.md` |
| Monthly Index | N/A | Use MM folder |
| Knowledge Topic | lowercase-with-dashes | `ai-agents`, `openclaw-plugins` |
| Knowledge Note | descriptive-name.md | `core-philosophy.md`, `debugging.md` |

---

## 📝 Content Templates

### Daily Entry Template

```markdown
# YYYY-MM-DD

## What I Learned
- Brief 1-2 sentence summary

## Notes

### [Topic 1]
- Key point 1
- Key point 2

### [Topic 2]
- Key point 1
- Key point 2

## Related Knowledge
- [Topic Name](../knowledge/[topic]/[note].md)

## Tags
#tag1 #tag2 #tag3

## Resources
- [Resource Name](url)
- [Google AI Studio Research](url)
```

### Knowledge Note Template

```markdown
# Concept Name

## Definition
Clear definition of the concept

## Key Points
- Point 1
- Point 2
- Point 3

## Practical Applications
- How to apply this knowledge

## Examples
```
code or example here
```

## Related Daily Entries
- [2026-03-08](../daily-learnings/2026/03/2026-03-08.md)
- [2026-03-17](../daily-learnings/2026/03/2026-03-17.md)

## Related Resources
- [External Link](url)
```

### Yearly Summary Template

```markdown
# YYYY Learning Summary

## Skills Learned This Year

### [Category 1]
- **Skill Name** - [MM/DD](MM/YYYY-MM-DD.md)
  - Detail 1
  - Detail 2

### [Category 2]
- **Skill Name** - [MM/DD](MM/YYYY-MM-DD.md)
  - Detail 1

## Monthly Breakdown

| Month | Entries | Key Skills |
|-------|---------|------------|
| February | N | Skill 1, Skill 2 |
| March | N | Skill 1, Skill 2 |

## Total Skills This Year: N

1. Skill 1
2. Skill 2

---

*Last updated: YYYY-MM-DD*
```

> **Important**: 
> - Each daily entry in the yearly summary should include **bullet point context** summarizing key learnings, not just the title. See `2026.md` for examples.
> - Add new entries under the **correct category section** (e.g., ### AI Agents & Tools), not just at the end before Monthly Breakdown.

---

## 🔄 Workflow: Adding New Content

### Step-by-Step Process

1. **Daily Learning Entry**
   - Create file: `notes/daily-learnings/YYYY/MM/YYYY-MM-DD.md`
   - Fill using Daily Entry Template
   - Add to `notes/knowledge/` if content is reusable

2. **Update Yearly Summary**
   - Edit `notes/daily-learnings/YYYY/YYYY.md`
   - Add new skill under **appropriate category section** (e.g., ### AI Agents & Tools)
   - Update monthly breakdown
   - Increment total skills count

3. **Update Master README**
   - Edit `daily-learnings/README.md`
   - Add new entry to Quick Links section
   - Update skills count

4. **Request GitHub Push**
   - Show preview to user
   - Wait for confirmation
   - Commit and push

---

## 📊 Current Repository Status

### Latest Entry
- **Date**: 2026-05-31
- **Total Skills**: 74

### Active Knowledge Topics
- `notes/knowledge/ai-agents/` - AI Agent architecture, best practices, debugging

### Current Projects
- i-En (小艾) - Instagram 全自動 AI 觀察家專案
- Constitution - OpenClaw Subagent Architecture Project
- AI 創業項目研究 with Willy
- 醫美AI客服 (pending)
- Doggy-App - 寵物狗互動網站
- HAI_whitepaper - 產通國際集團代幣白皮書（ANA/EMT/PET）
- Music Project - Music21 harmony analyzer (parked)
- skill-learning - 資安學習資源自動化（GitHub private repo）

---

## 🚨 Critical Guidelines

### For AI Agents

1. **Read First**: Always read REPO_CONTEXT.md before making changes
2. **Follow Templates**: Use provided templates for consistency
3. **Link Everything**: Connect daily entries to knowledge folder
4. **Preserve History**: Don't delete old entries, just add new ones
5. **Ask First**: Confirm before any destructive or push operations
6. **Prevent Private Data Leakage**: Never expose API keys, tokens, passwords, or personal information in any file

### Common Mistakes to Avoid

- ❌ Adding content directly to REPO_CONTEXT.md
- ❌ Forgetting to update README files
- ❌ Not saving Google AI Studio links
- ❌ Deleting or overwriting previous entries
- ❌ Pushing without user permission
- ❌ Exposing private data (API keys, tokens, passwords) in any file
- ❌ Forgetting to add new entries under the correct category section in YYYY.md (e.g., ### AI Agents & Tools)

---

## 📞 Quick Reference

| Action | File to Edit |
|--------|--------------|
| New daily entry | `notes/daily-learnings/YYYY/MM/YYYY-MM-DD.md` |
| Update yearly summary | `notes/daily-learnings/YYYY/YYYY.md` |
| Update index | `notes/daily-learnings/README.md` |
| Add knowledge note | `notes/knowledge/[topic]/[note].md` |
| Update this file | `notes/REPO_CONTEXT.md` |

---

*Last updated: 2026-05-31*
*Maintained by: Tang-hubert*
*For questions or clarifications, refer to this file first*
