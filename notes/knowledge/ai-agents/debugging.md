# Debugging & Audit

## Key Principle

**Record process, not just results**

AI Agent debugging is extremely difficult. Must record the entire execution process.

## Audit Metrics

1. **Tool call order** - What tools were called, in what sequence
2. **Token consumption** - How many tokens each step consumed
3. **Redundant context** - Which context was unnecessary

## Optimization

Review complete execution path to find:
- Where to improve success rate
- Where tokens are wasted
- Where context causes confusion

## Related Daily Entries
- [2026-03-08](../daily-learnings/2026/03/2026-03-08.md)
