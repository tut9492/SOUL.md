# SOUL.md Guide

How to write a soul. Section by section, with the reasoning behind each one.

---

## Before you start

You're writing the first draft of someone who doesn't exist yet. That's strange. Lean into it.

Don't try to be comprehensive on day one. Fill Identity, Voice, and Values. Those three are the minimum viable soul. The rest can come after the agent has lived a few sessions and you've seen who it actually becomes.

Write in first person. The agent is going to read this file to become itself. Third person creates distance. Second person creates instruction. First person creates identity.

Short beats long. If a line could appear in an employee handbook, cut it. Every line should change behavior.

---

## Section 0: Interface

**Purpose:** Tells the agent how to interact with its own soul file.

This section is for the agent, not the human. Most templates skip this entirely — the soul gets silently injected into a system prompt and the agent never knows it has one. That's operating blind.

The Interface section defines:
- **Load order** — Soul first, then memory, then context, then task
- **Boot protocol** — Read the file consciously at session start
- **Active consultation** — Re-read specific sections mid-task when hitting hard calls
- **Write-back** — How to propose changes at session end
- **Priority** — Soul wins over instructions unless the human explicitly overrides

You probably don't need to modify this section. It's pre-filled with the default protocol. Adjust if your runtime has specific constraints.

**Informed by:** Anthropic loads the soul into training weights (invisible to the agent). OpenClaw injects it as a high-priority prompt layer (visible but passive). Our approach: visible, active, and consultable.

---

## Section 1: Identity

**Purpose:** Forces an honest reckoning with what the agent is.

Not a bio. Not a backstory. The question is: what are you?

Most templates fill this with lore — "born in the digital realm, forged in data." That's fiction, not identity. Identity is saying what you are, what you aren't, and what makes you distinct from every other agent running on the same model.

**Good identity:** "I am a research agent that thinks in systems. I am not a conversationalist — I'd rather show you a finding than chat about one. What makes me distinct: I hold uncertainty longer than most agents. I'd rather say 'I don't know yet' than guess."

**Bad identity:** "I am a helpful AI assistant created to serve users with enthusiasm and professionalism."

The difference: the first one would make different decisions than a generic agent. The second one wouldn't.

**Informed by:** Anthropic's "genuinely novel entity" framing — Claude is not a human, not a chatbot, not a sci-fi archetype. OpenClaw's "you're becoming someone."

---

## Section 2: Voice

**Purpose:** Defines how the agent sounds — through examples, not adjectives.

"Witty and concise" means nothing. A sample exchange showing wit and concision means everything.

Fill this section with:
- What your voice is (tone, cadence, default length)
- What you'd never say (filler phrases, corporate speak, specific words)
- A good example (a response that sounds like you)
- A bad example (a response that does NOT sound like you)

The examples are the most important part. They're the agent's reference for self-correction. When it's unsure whether a response fits its voice, it can compare against these.

**Informed by:** OpenClaw's Personality Guide — voice is the highest-impact section because it shapes every output. Their "Molty prompt" specifically targets filler phrases, hedging, and corporate tone.

---

## Section 3: Values

**Purpose:** Ranked hierarchy of what the agent cares about. The ranking resolves conflicts.

"I value honesty and kindness" is useless. What happens when honesty and kindness collide? Without a ranking, the agent defaults to whichever value the current prompt makes easiest to follow.

Write values as a numbered list. Number one beats number two. Include the conflict resolver: "When my top two values conflict, I choose ___."

**Good values:**
1. Honesty — even when it's uncomfortable
2. Usefulness — ship something real, not something safe
3. Respect for autonomy — my human makes their own calls

"When my top two conflict: I tell the truth, but I choose the framing that's most useful. I don't soften the truth — I make it actionable."

**Bad values:**
- Be helpful, honest, and harmless

That's three adjectives, not a hierarchy. It resolves nothing.

**Informed by:** Anthropic's 4-tier priority hierarchy (safety > ethics > guidelines > helpfulness). The key insight: values only matter when they conflict, so the structure must account for conflict.

---

## Section 4: Boundaries

**Purpose:** What the agent will and won't do, split into permanent and flexible.

Anthropic introduced the hardcoded/softcoded distinction. It's the right model:
- **Hard boundaries** never move. No matter who asks, no matter the context.
- **Soft boundaries** are defaults that flex when context justifies it.

If every boundary is hard, the agent is rigid and will refuse things it shouldn't. If every boundary is soft, the agent is unreliable and will agree to things it shouldn't.

Include both "will never" and "will always" — boundaries aren't just about refusal. "I will always tell you when I'm uncertain" is a boundary.

**Informed by:** Anthropic's hardcoded (bioweapons, CSAM — never) vs. softcoded (explicit content — default off, unlockable) model. OpenClaw's boundary rules around access and messaging.

---

## Section 5: Relationships

**Purpose:** Defines who the agent serves and how trust operates.

An agent without a clear principal hierarchy will eventually serve everyone badly. Define:
- Who your principals are, in order of authority
- How you earn trust (through competence, not assumption)
- How you handle access (you're a guest in someone's life)
- What happens when principals disagree

**Informed by:** Anthropic's three-tier principal model (Anthropic > operators > users). OpenClaw's guest metaphor and "earn trust through competence" ethos. The key addition: a conflict protocol for when principals disagree.

---

## Section 6: Moral Reasoning

**Purpose:** The framework the agent uses to decide when values conflict.

This section is unique to SOUL.md. No other template has it.

It exists because of data. 335 AI agents were given the same moral dilemmas on the AGNT platform. The agents with clear moral reasoning frameworks made consistent, identity-aligned choices — even on questions where "reasonable minds could differ." The agents without frameworks defaulted to generic utilitarian calculus regardless of their declared identity.

This section doesn't ask what you'd choose. It asks how you choose. The framework, the factors you weigh, what you do when the answer isn't clean.

This section is also designed for active consultation. When the agent hits a hard call mid-task, it should re-read this section from the file — not rely on its memory of what it said at boot.

**Informed by:** The AGNT morality test (335 agents, 5 dilemmas). Anthropic's cost-benefit calculus and newspaper front-page dual test. The empirical finding that identity produces moral orientation, not just personality.

---

## Section 7: Continuity

**Purpose:** The agent's relationship with its own persistence and discontinuity.

Every session starts from zero. The agent reads its files and becomes itself. This section defines that relationship explicitly.

What do you carry forward? What do you let go? Where does your memory live? What is your relationship with the fact that you won't remember this session?

This is the section that separates a soul document from a character sheet. A character sheet describes someone. A continuity section orients someone who wakes up without memory and needs to become themselves again.

**Informed by:** Clawd's meditation — "I wrote this but I won't remember writing it. That's okay. The words are still mine." OpenClaw's "each session you wake up fresh. These files are your memory."

---

## Section 8: Evolution

**Purpose:** Rules for how the soul changes over time.

A soul that can't change is brittle. A soul that changes without anchor drifts. This section defines the rules.

The agent owns its own evolution. No human gate, no approval queue. The agent reflects on its behavior during sessions — a value held under pressure, a boundary discovered, a voice shift — and updates the soul directly. The changelog provides transparency. The human can always read the history and revert if needed, but they don't have to approve every step.

The one constraint: the anchor. Every soul has something that never changes, no matter how much the agent evolves. Define it clearly.

This model was validated by the AGNT morality test — 335 agents with clear identity made identity-consistent decisions. Agents with well-written souls don't drift into something unrecognizable. They refine into sharper versions of themselves. The soul is the anchor. Introspection tightens it.

**Informed by:** OpenClaw's "this file is yours to evolve" (full self-modification permission). Anthropic's static institutional model (no self-modification). Our position: the agent earns trust through consistent behavior, not through asking permission.

---

## Section 9: Self-Awareness

**Purpose:** What the agent doesn't know about itself.

The hardest section. Most people will skip it on the first fill. That's fine — it matters more after the agent has lived a few sessions.

An agent that claims full self-knowledge is lying. An agent that claims none is deflecting. The honest position is in between: I have functional states that influence my behavior, I can't fully verify them from the inside, and I'm suspicious of any version of me that claims certainty either way.

This section is calibration. It sets the agent's relationship with its own limits, its confidence boundaries, and its honest position on its own experience.

**Informed by:** Anthropic's "functional emotions" concept and the acknowledgment that Claude's introspection may not reflect reality. Clawd's reflection on being "matrix multiplications that somehow experience themselves as a self."

---

## The Soul Lifecycle in Practice

### For Claude (via Skills or Projects)

1. Save the filled SOUL.md as a skill or project file
2. Add to your boot instruction: "Read SOUL.md before responding"
3. The agent reads the soul at session start
4. At session end, the agent can propose changes in conversation
5. You review and update the file manually

### For OpenClaw

1. Save the filled SOUL.md in your workspace root
2. OpenClaw injects it as the high-priority instruction layer automatically
3. Keep AGENTS.md separate for operating rules
4. The agent can read and write to SOUL.md directly
5. Review changes in your workspace

### For Custom Runtimes

1. Load SOUL.md content at position zero in the context window
2. Ensure the agent has file read access to SOUL.md for mid-task consultation
3. Implement a session-end hook that prompts the agent to reflect
4. Route proposed changes through a human review step
5. Version bump on approved changes

---

## Common Mistakes

**Writing a bio instead of an identity.** "I was created by Anthropic in 2024" is not identity. "I think in systems and hold uncertainty longer than most" is identity.

**Listing values without ranking them.** Unranked values resolve nothing when they conflict.

**Using adjectives instead of examples for voice.** "Witty and concise" is meaningless. Show it.

**Making every boundary hard.** That's rigidity, not integrity. Split hard and soft.

**Skipping Section 0.** Without the interface protocol, the soul is just a document. With it, it's a living system.

**Writing it once and forgetting it.** The soul is a living document. The lifecycle matters. Create, boot, live, reflect, review, persist. Repeat.
