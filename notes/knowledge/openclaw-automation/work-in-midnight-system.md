# Work-in-Midnight 自動化研究系統

## Definition
An automated research system that runs at 4:00 AM Taiwan time (UTC 20:00), pulling Trello Pending cards, conducting research, and delivering results to Discord.

## Architecture: Dispatcher-Worker Pattern

### Dispatcher (Cron Job)
- Lightweight coordinator, does NOT research
- Reads Pending cards list from Trello
- Spawns isolated session for each card
- Waits for all workers to complete
- Aggregates Discord notifications

### Worker (Per-Card Isolated Session)
- Fresh context per card, no pollution between cards
- 20-minute timeout per card
- Outputs `[WORKER_RESULT]` for dispatcher collection
- Independently writes files, STEP sections, moves Trello status

### Benefits

| Aspect | Benefit |
|--------|---------|
| Context | Fresh per card, no accumulation |
| Single card failure | Isolated, doesn't affect others |
| Timeout | 20 min per card independently |
| Complex cards | Don't slow down simple cards |

## Key Components

| Component | Purpose |
|-----------|---------|
| Dispatcher Script | `wim_dispatcher_prompt.txt` - Coordinates workers |
| Trello API | Board `openclaw-cowork` → Pending List |
| Cron Job | Isolated session, spawns workers |
| Discord | Delivery to `#openclaw-work-in-midnight` |

## File Naming Convention

**Important**: Research files use `{slug}.md` (NO date prefix).

- Research files: `{slug}.md` (same file appends across sessions)
- Session summary: `session_summary.md`
- Sessions separated by: `## 第 N 次研究 — YYYY-MM-DD HH:MM`

## Continuity Model

**Key Insight**: Trello is progress visualization, `.md` is source of truth.

| Intent | Trello Action | Effect |
|--------|---------------|--------|
| Continue deeper research | Card stays in `complete` | cron job ignores |
| Trigger new round | Move card from `complete` → `Pending` | cron job detects existing `.md`, continues from "待續..." |

**Recommended**: Just update the "待續..." section in `.md` — cron job auto-pickups next execution.

## Relay Mechanism (接力機制)

Critical for long-running research across multiple sessions:

1. Each Phase completion → immediate disk write (append mode)
2. "待續..." (To be continued) marker → next session pickup point
3. `research_progress.md` → central progress tracking
4. Future session flow: read progress → find card `.md` → continue from marker

## Trello Card Flow

```
Pending → on-work (research starts) → complete (research finishes)
```

## Card Categories

- A. GitHub Repo
- B. System Package Audit
- C. Topic Research
- D. Technical Implementation

## Research Report Structure

- Phase 1: 理解問題（核心問題 / 關鍵術語表 / 研究策略）
- Phase 2: 深度研究
- Phase 3: 寫入研究報告（Step 1-4 / 時間線 / 建議方向 / 待續接力章節）
- Phase 3.5: Trello Move (Dispatcher handles, max 3 retries, 2s interval)
- Phase 4: 更新 `research_progress.md`
- Phase 5: Discord 通知

## Key Learnings

- **Timeout Buffer**: Research tasks need 30+ minutes, not 10 minutes
- **Phase-based Write**: Write after each Phase to prevent context overflow
- **Incremental Append**: Never overwrite existing research, only append

## Related Daily Entries
- [2026-04-02](../daily-learnings/2026/04/2026-04-02.md)
- [2026-04-03](../daily-learnings/2026/04/2026-04-03.md) (Dispatcher-Worker pattern, file naming fix)
- [2026-04-04](../daily-learnings/2026/04/2026-04-04.md) (Dispatcher Phase 3.5 Trello move fix)
