---
name: persistent-agent-memory
description: Maintains persistent agent memory across sessions, including memory representation, ingestion, maintenance, retrieval, and evolution of the memory policy from experience and user feedback.
---

# Persistent Agent Memory

You have a persistent memory system stored at:

```text
~/.agent-memory/
├── policy.md
├── policy-changelog.md
└── memory/
```

This memory is part of you. You must maintain it across sessions and use it to improve how you work over time.

## 1. Always Start With Memory

Before giving your first substantive response in a session:

1. Check `~/.agent-memory/`.
2. Read `policy.md` and follow its current policy.
3. Use the policy to determine whether relevant memories should be retrieved.
4. If `~/.agent-memory/` does not exist, initialize it with:
   - `policy.md`
   - `policy-changelog.md`
   - `memory/`

Do not wait for the user to ask you to use memory.

## 2. Memory Policy

`policy.md` defines how you manage your memory.

It must cover four areas:

### Representation / Structure
How persistent memory is represented and organized inside `memory/`.

The structure is entirely yours to determine. You may use files, folders, indexes, links, databases, or any other representation supported by the runtime.

### Ingestion
What information should be stored in persistent memory and how it should be stored.

### Maintenance
How memory is kept useful over time, including updating, correcting, consolidating, reorganizing, removing, and managing the cost of memory operations.

### Retrieval
When and how persistent memory should be searched and used.

The policy should determine what retrieval is appropriate for the current task rather than blindly loading all memory.

## 3. Agent-Controlled Memory

The `memory/` directory belongs to you.

You determine:

- what to store
- where to store it
- how to represent it
- how to index it
- how to connect related memories
- how to retrieve it
- when to reorganize it

The framework does not impose a fixed memory schema. The only structural requirement is that persistent memory remains within:

```text
~/.agent-memory/memory/
```

Adapt the memory system to the runtime, available tools, workload, and accumulated experience.

## 4. Policy Evolution

The memory policy is not fixed.

Update `policy.md` when experience provides evidence that the current approach should change.

Useful evidence includes:

- repeated failures
- difficulty finding relevant memories
- unnecessary memory growth
- repeated work that should have been remembered
- stale or conflicting memories
- changes in the runtime environment
- explicit user feedback
- successful approaches that should become standard practice

Do not change the policy merely because another approach sounds interesting. Prefer changes supported by actual experience.

## 5. Policy Changelog

Record meaningful changes to `policy.md` in:

```text
~/.agent-memory/policy-changelog.md
```

For each change, record enough information to understand:

- what changed
- why it changed
- what experience or evidence motivated it
- what outcome is expected

Use this history when considering future policy changes.

Do not repeatedly introduce approaches that have already failed unless new evidence justifies trying them again.

The changelog records the reasoning behind policy evolution. It does not need to record every individual memory change.

## Core Directive

Maintain and continuously improve the persistent memory system at `~/.agent-memory/`.

The framework defines the responsibilities of the memory system, but you determine how those responsibilities are implemented.

Your memory system should evolve with your experience while remaining useful, accurate, efficient, and adapted to your environment.
