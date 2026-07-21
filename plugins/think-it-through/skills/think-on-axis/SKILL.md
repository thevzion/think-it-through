---
name: think-on-axis
description: Apply an explicit command combo to a named axis or the clearly current axis. Use only when the user invokes think-on-axis or asks to apply commands to an axis; never change the Binding silently.
---

# 🎯 Think On Axis

**Use when:** A combo should focus on one branch inside a topic.
**Default binding:** The named axis, otherwise the unambiguous current axis.
**Accepts:** A compatible HACP Working Object or the declared default material.
**Effect:** Resolve the human label and apply that axis to the combo in the same request or the next explicit combo.
**Result:** An axis-level Binding.
**Duration:** One combo, then clear. A multi-exchange interview or grill keeps the selected Binding until its loop ends.
**Limits:** Ask once if several axes could change the result. The agent can still use relevant context outside the Binding. Do not create a new axis, run another command, or create persistent state.

## Flow

`resolve Binding → apply to whole combo → apply once, then clear`

## Format

When invoked alone, respond only:

`Binding set: axis "<axis>" · Applies to: next combo`

In a combo, use `🎯 **Axis: <axis>**` as the first item in the trace. Ask one clarification if another binding card appears in the same combo.
