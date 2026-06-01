# Context Engineering

## Problem: Context Pollution

When tools and history info are too many → AI attention分散 → performance下降

## Solution: Planner-Executor Architecture

### Planner (规划者)
- Has global information
- Responsible for dispatching tasks

### Executor (执行者)
- Focuses on specific task
- Only sees necessary context for current step

## Core Principle

**Precision filtering**: Model should ONLY see info it MUST see for current step.

This is the core of context engineering - let model focus on current step.

## Related Daily Entries
- [2026-03-08](../daily-learnings/2026/03/2026-03-08.md)
