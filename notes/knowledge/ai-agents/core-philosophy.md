# Core Philosophy: Simple & Cruel

## Hierarchy

```
API Call > Workflow > Agent
```

### API Call
If a task can be solved with ONE simple API call (prompt), use API call.

### Workflow
If task has multiple steps but steps are FIXED and DETERMINISTIC (no human intervention needed), use Workflow.

### Agent
Use Agent ONLY when:
- Task needs human involvement (aesthetic judgment, iterative refinement)
- Options grow exponentially, can't design individual frontend for each

## Skills vs Prompts

- **Agent fails → not bad prompts, but LACK OF TOOLS**
- Give Agent necessary tools → "emergence" happens (1+1>2)
- Start with simple SDK, not LangGraph

## Prompting Strategy

- DON'T copy-paste big company prompts (Token爆炸)
- Start with ZERO constraints → observe AI's native response
- Iterate: add constraints based on AI behavior, not upfront

## Summary

Run first, then optimize. Don't let "elegant architecture" become a blocker. Start simple, add complexity only when needed.

## Related Daily Entries
- [2026-03-08](../daily-learnings/2026/03/2026-03-08.md)
