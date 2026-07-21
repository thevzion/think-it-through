---
name: think-on-topic
description: Apply an explicit command combo to a named topic or the clearly current topic. Use only when the user invokes think-on-topic or asks to apply commands to a topic; never change the Binding silently.
---

# 🎯 Think On Topic

**Use when:** A combo should focus on one topic and its relevant axes.
**Default binding:** The named topic, otherwise the unambiguous current topic.
**Accepts:** A compatible HACP Working Object or the declared default material.
**Effect:** Resolve the human label and apply that topic to the combo in the same request or the next explicit combo.
**Result:** A topic-level Binding.
**Duration:** One combo, then clear. A multi-exchange interview or grill keeps the selected Binding until its loop ends.
**Limits:** Ask once if several topics could change the result. The agent can still use relevant context outside the Binding. Do not run another command or create persistent state.

## Flow

`resolve Binding → apply to whole combo → apply once, then clear`

## Format

When invoked alone, respond only:

`Binding set: topic "<topic>" · Applies to: next combo`

In a combo, use `🎯 **Topic: <topic>**` as the first item in the trace. Ask one clarification if another binding card appears in the same combo.
