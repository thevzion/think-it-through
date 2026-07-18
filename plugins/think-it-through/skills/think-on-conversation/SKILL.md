---
name: think-on-conversation
description: Apply an explicit command combo to the entire available conversation. Use only when the user invokes think-on-conversation or asks to apply commands conversation-wide; never change the focus silently.
---

# 🎯 Think On Conversation

**Context:** The full relevant conversation and explicitly supplied material.
**Use when:** A combo should cover every available topic and axis.
**Applies to by default:** The full available conversation plus supplied checkpoints.
**Job:** Resolve the conversation focus and apply it to the combo in the same request or the next explicit combo.
**Result:** A conversation-wide focus.
**Runs for:** One combo, then clear. A multi-turn interview or grill keeps the selected focus until its loop ends.
**Limits:** Change only the focus. The agent can still use relevant context outside the focus. Do not imply unavailable history, run another command, or create persistent state.
**Combines with:** Apply before all jobs in semantic order, even when written elsewhere. The first job works on this focus; later jobs work on the preceding result.

## Flow

`resolve focus → apply to whole combo → apply once, then clear`

## Format

When invoked alone, respond only:

`Focus set: conversation · Applies to: next combo`

In a combo, use `🎯 **Conversation**` as the first item in the trace. Ask one clarification if another selector appears in the same combo.
