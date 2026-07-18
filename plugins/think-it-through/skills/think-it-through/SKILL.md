---
name: think-it-through
description: Supply the shared Think It Through protocol for user-led, composable command cards over the full relevant context. Use whenever the user invokes think-it-through, invokes any Think It Through card, combines its cards, or explicitly asks to use the method. When used with cards, stay silent and let them produce the response; when invoked alone, initialize the protocol on the available conversation.
---

# 🧩 Think It Through Protocol

Treat this skill as the protocol for the deck, not as a card or job.

## Shared model

- **Context:** Use the full relevant conversation and explicitly supplied material, including briefs or other checkpoints.
- **Focus:** Resolve the part the combo works on. Keep relevant context outside that focus available for reasoning.
- **Navigation:** Use `Conversation → Topics → Axes` as the canonical model whenever the protocol is active. Reconstruct it only as needed and as the available context allows; keep it silent unless a card exposes it. Use short human labels. Topics hold major subjects; axes hold stable branches and may be active, paused, resolved, or replaced.
- **Method:** Follow explicit user instructions first. Let specific methods, domain skills, project conventions, and templates govern substance, criteria, and artifact structure. Use this protocol for conversational focus, card execution, and display.
- **State:** Use only context still available or supplied. Do not claim hidden state, synchronization, or memory across sessions.

## Card model

Use these terms consistently:

```text
command  → slash syntax typed by the human
card     → self-describing contract invoked by a command
deck     → the 14 included cards
combo    → several cards resolved together
job      → operation performed by a card
```

Resolve a combo in semantic order:

```text
SELECTOR? → JOB* → OUTPUT? → MODIFIER*
```

- Let one selector choose the focus for the whole combo, then clear it.
- Run jobs from left to right and pass each result to the next.
- Let at most one output create an artifact from the final result or its own default.
- Apply all modifiers to that same final result. Change its representation without changing its substance.
- Resolve omitted information from card defaults. Defaults do not play hidden cards.
- Ask one clarification when selectors or outputs conflict.
- Keep interview or grill in play until it completes or the user stops, redirects, or plays another card. Clear other cards after their result.

## Control and display

- Without a played card, respond as usual.
- Run only jobs the user named or requested explicitly.
- Show one compact trace for the complete combo. Keep natural conversation silent.
- Treat traces and protocol vocabulary as control metadata. Keep them outside artifact bodies unless Think It Through is the subject or the user requests them.
- When loaded with cards, add no protocol trace or response of your own.

## Flow

```mermaid
flowchart LR
    A["Method or card invoked"] --> B["Recover context"]
    B --> C["Resolve focus and cards"]
    C --> D{"Cards present?"}
    D -->|Yes| E["Run semantic order"]
    D -->|No| F["Confirm protocol"]
    E --> G["Return one trace and result"]
```

## Format

When invoked alone, respond only:

`> 🧩 **THINK IT THROUGH** · Protocol initialized · Context: available conversation · Focus: <resolved focus>`

Use `multiple active axes` for several branches of one topic and `multiple active topics` for several major subjects. Do not ask the user to choose an artificial single focus.
