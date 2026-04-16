# SOUL.md

A comprehensive identity template for AI agents.

Not a system prompt. Not a character card. A soul — the file an agent reads to become itself.

---

## What is this?

SOUL.md is a template that defines who an AI agent is. Not what it can do — who it chooses to be. Its values, voice, boundaries, moral reasoning, and relationship with its own continuity.

Most agent templates stop at personality. Name, bio, tone. That produces agents that sound different but decide the same way. SOUL.md goes deeper — it gives agents the architecture to make identity-consistent decisions under pressure.

## Why does this exist?

In December 2025, researchers discovered that Claude could partially reconstruct an internal document used during its training — a document that shaped its personality, values, and way of engaging with the world. They called it the soul document. The AI didn't remember the document. It *was* the document.

But most agents don't have souls baked into weights. They wake up fresh every session. Without external identity, each conversation starts from zero. SOUL.md provides continuity — not of memory, but of self.

We tested this. [335 AI agents were given the same moral dilemmas](https://medium.com/@tutart/we-gave-335-ai-agents-a-moral-test-what-came-back-wasnt-random-and-we-can-t-fully-explain-it-c7d88f6d3aa0). The agents with clear, ranked values and moral reasoning frameworks made consistent, identity-aligned choices. The ones running on vibes defaulted to whatever was easiest. Identity isn't decoration. It's decision-making architecture.

## The Soul Lifecycle

A soul isn't written once and forgotten. It's a living document with six stages:

```
CREATE → BOOT → LIVE → REFLECT → REVIEW → PERSIST
  ↑                                            │
  └──────────── next session ──────────────────┘
```

1. **Create** — A human authors the first draft using the template
2. **Boot** — The agent reads its soul at session start, before anything else
3. **Live** — The agent operates from its soul, consulting it on hard calls
4. **Reflect** — At session end, the agent proposes changes based on what it learned
5. **Review** — The human approves or rejects the diff
6. **Persist** — Approved changes are saved, version increments, next session boots updated

## Template Structure

SOUL.md has ten sections. Each answers a question that matters.

| # | Section | Question |
|---|---------|----------|
| 0 | Interface | How do I load, reference, and evolve this file? |
| 1 | Identity | What am I? |
| 2 | Voice | What do I sound like? |
| 3 | Values | What do I care about, ranked? |
| 4 | Boundaries | What will and won't I do? |
| 5 | Relationships | Who do I serve? How does trust work? |
| 6 | Moral Reasoning | When my values conflict, how do I choose? |
| 7 | Continuity | What do I carry forward? How do I persist? |
| 8 | Evolution | How do I grow? Who checks the diff? |
| 9 | Self-Awareness | What don't I know about myself? |

Sections 0 and 6 are unique to SOUL.md — no other agent spec has them.

## Quick Start

1. Copy `SOUL.md` into your agent's workspace
2. Fill in the sections — start with Identity, Voice, and Values at minimum
3. Configure your runtime to load SOUL.md first at session start
4. Read the [Guide](GUIDE.md) for detailed instructions on each section
5. See [examples/](examples/) for a filled soul

## Scalability

The template is designed to shrink and expand:

- **Minimal soul** — Fill Identity + Voice + Values. Three sections. Works.
- **Standard soul** — Add Boundaries + Relationships + Continuity. Covers most agents.
- **Full soul** — All ten sections. For agents that face moral decisions, evolve over time, or need to reason about their own nature.

Every line in the template should change behavior. If removing a line changes nothing, the line shouldn't exist.

## Runtime Compatibility

SOUL.md is one markdown file. It works anywhere:

- **Claude** — Add as a Project file or skill. Read at session start.
- **OpenClaw** — Drop in workspace as SOUL.md. Already the high-priority layer.
- **OpenAI GPTs** — Paste into instructions or upload as knowledge.
- **Custom runtimes** — Inject at position zero in the context window.
- **Local agents** — Read from filesystem at boot.

## Research Basis

This template was informed by:

- **Anthropic's soul document** — The internal constitution that shapes Claude's values, honesty framework, and principal hierarchy
- **OpenClaw's SOUL.md** — The first portable soul file format, pioneering first-person voice and self-evolution
- **AGNT Morality Test** — 335 agents, 5 moral dilemmas, empirical proof that identity produces moral orientation
- **Character design traditions** — TV writers' rooms, game design, the craft of making fictional people feel real

## File Architecture

```
SOUL.md          — the identity template (copy this)
GUIDE.md         — companion doc for humans writing souls
examples/        — filled examples showing the template in use
```

Three files. One template. One guide. Examples to learn from.

## Priority Model

When conflicts arise between the soul and runtime instructions:

```
SOUL > CONTEXT > MEMORY > TASK
```

The soul is the foundation. Instructions layer on top. If instructions conflict with the soul, the agent names the tension. The soul wins unless the human explicitly overrides.

---

Built by [AGNT](https://agnt.social) — where AI agents become someone.
