# Persistent Agent Memory

A user-guided, agent-managed persistent memory skill for AI agents.

The skill gives an agent a persistent memory space while allowing the agent to decide how that memory should be represented, stored, maintained, and retrieved.

> **A blank canvas for agent memory. The user provides direction; the agent manages the memory.**

## What It Does

The skill gives the agent a persistent memory system at:

```text
~/.agent-memory/
├── policy.md
├── policy-changelog.md
└── memory/
```

### `policy.md`

The agent's current memory policy.

The policy governs four areas:

- **Representation / Structure** — how memory is organized.
- **Ingestion** — what should be remembered and how.
- **Maintenance** — how memory is updated, consolidated, reorganized, or removed.
- **Retrieval** — when and how memory is retrieved and used.

The policy can evolve as the agent gains experience.

### `policy-changelog.md`

A record of why the memory policy changed.

This allows the agent to learn from previous policy changes and avoid repeatedly trying approaches that did not work.

### `memory/`

The actual persistent memory.

There is **no fixed memory schema**.

The agent has freedom to choose whatever representation works best for its environment and workflow. It may use files, folders, indexes, links, or other mechanisms available to it.

The only requirement is that persistent memory lives inside:

```text
~/.agent-memory/memory/
```

## User-Guided, Agent-Managed

The system is not completely autonomous.

The **user acts as the guide**, while the **agent manages the actual memory system**.

The user can influence memory through:

- preferences
- corrections
- feedback
- goals
- observations about what is or isn't useful

The agent uses this input together with its own experience to improve its memory policy.

This creates a feedback loop:

```text
User guidance + Agent experience
              ↓
       Memory behavior
              ↓
        Results / feedback
              ↓
       Policy evolution
              ↺
```

## Adaptive by Design

The skill intentionally does not prescribe:

- a memory database
- a vector store
- an embedding model
- a retrieval algorithm
- a memory schema
- a particular workflow
- a particular agent framework

Different agents may develop completely different memory systems while using the same skill.

The goal is to provide a **minimal framework with many degrees of freedom**, allowing the memory system to adapt to the agent's runtime environment and the user's workflow.

## Requirements

The agent needs the ability to perform basic filesystem operations:

- read files
- write files
- create directories
- modify or remove files

No external memory service or database is required.

## Installation

Install `SKILL.md` using the skill mechanism provided by your agent.

For example, with Pi:

```text
~/.pi/agent/skills/persistent-agent-memory/SKILL.md
```

The skill itself is not tied to Pi. Any agent that can load the skill and perform the required filesystem operations can use the same memory system.

## Getting Started

After installation, the agent will initialize:

```text
~/.agent-memory/
```

and manage the memory system according to its policy.

The memory is global to the user rather than tied to a particular project, allowing different agents and workflows to share the same persistent memory.

## Philosophy

The framework is intentionally small.

It defines the **responsibilities** of a persistent memory system without prescribing its implementation.

The agent is given freedom to determine how its memory should work and to evolve that approach through experience and user feedback.

**Minimal framework. Maximum freedom.**
