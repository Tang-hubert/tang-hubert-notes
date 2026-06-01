# Memory Management

## Pass by Reference, Not Data

- DON'T let AI repeatedly read/write large data (expensive Output Token cost)
- DON'T let AI output whole code blocks (AI容易产生"过早修正"错误)
- **Solution**: Store large data in file system, pass "pointer/file ID" between Agents

## Memory Types

### Internal Memory
- Only valid for current conversation
- Disappears when conversation ends
- Purpose: Prevent interference with next round

### External Storage
- Persistent across sessions
- Use for: To-do lists, state tracking, long-term tasks
- Store in: File system, database

## Best Practices

- Agent: "I have reviewed file X, now preparing action Y"
- Instead of: Agent outputting whole code for confirmation

## Related Daily Entries
- [2026-03-08](../daily-learnings/2026/03/2026-03-08.md)
