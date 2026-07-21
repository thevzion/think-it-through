---
name: think-on-conversation
description: Apply an explicit command combo to the entire available conversation. Use only when the user invokes think-on-conversation or asks to apply commands conversation-wide; never change the Binding silently.
---

# 🎯 Think On Conversation

**Use when:** A combo should cover every available topic and axis.
**Default binding:** The full available conversation plus supplied checkpoints.
**Accepts:** A compatible HACP Working Object or the declared default material.
**Effect:** Resolve the conversation Binding and apply it to the combo in the same request or the next explicit combo.
**Result:** A conversation-wide Binding.
**Duration:** One combo, then clear. A multi-exchange interview or grill keeps the selected Binding until its loop ends.
**Limits:** Change only the Binding. The agent can still use relevant context outside it. Do not imply unavailable history, run another command, or create persistent state.

## Flow

`resolve Binding → apply to whole combo → apply once, then clear`

## Format

When invoked alone, respond only:

`Binding set: conversation · Applies to: next combo`

In a combo, use `🎯 **Conversation**` as the first item in the trace. Ask one clarification if another binding card appears in the same combo.
