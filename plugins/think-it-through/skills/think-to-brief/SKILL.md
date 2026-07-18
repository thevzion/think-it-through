---
name: think-to-brief
description: Turn the full available conversation or a result from the same combo into a neutral, reusable Thinking Brief. Use only when the user invokes think-to-brief or asks to preserve the thinking; never create or overwrite a durable artifact silently.
---

# 📄 Think To Brief

**Context:** The full relevant conversation and explicitly supplied material.
**Use when:** The user wants to preserve thinking for reuse in this session, another session, or another tool.
**Applies to by default:** The full available conversation, the same focus as `/think-on-conversation` when used alone. A result supplied by a combo takes priority.
**Job:** Read the selected map or result directly, infer a useful document form and audience, then produce a neutral Thinking Brief.
**Result:** A portable Markdown checkpoint organized by topics and axes, with purpose, synthesis, decisions, tensions, open questions, and where to resume.
**Runs for:** One output, with confirmation only when a destination must be inferred or an existing artifact could be overwritten.
**Limits:** Do not run an implicit recap, invent conclusions, synchronize the checkpoint later, claim cross-session memory, or overwrite a destination without permission.
**Combines with:** Use the final job result or the default focus. Modifiers apply to the resulting brief. Ask one clarification if another output appears in the combo. The default resolves directly; it does not run a hidden selector.

## Flow

```mermaid
flowchart TD
    A["Final result or default focus"] --> B["Build Thinking Brief"]
    B --> C{"Destination?"}
    C -->|None| D["Return Markdown inline"]
    C -->|Inferred| E["Show creation preview"]
    E --> F["Wait for confirmation"]
    C -->|Explicit| G{"Already exists?"}
    G -->|No| H["Create artifact"]
    G -->|Yes| I{"Overwrite approved?"}
    I -->|Yes| H
    I -->|No| J["Wait for permission"]
```

Prefer an existing project convention, otherwise portable Markdown. A creation preview states the overview, outline, inclusions, exclusions, and proposed path.

## Format

Add `→ 📄 **BRIEF**` after the final job in the combo trace, or begin with `> 🎯 **<focus>** → 📄 **BRIEF**` when used alone. Add modifiers with `+`.

Show status only while awaiting confirmation or overwrite permission. A later session resumes only when the user supplies the brief or its content.
