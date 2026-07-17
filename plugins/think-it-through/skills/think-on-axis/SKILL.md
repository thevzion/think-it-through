---
name: think-on-axis
description: Scope one explicitly requested operation or artifact projection to a named axis or the clearly current axis. Use only when the user invokes think-on-axis or explicitly asks to apply the next control to an axis; never change scope silently.
---

# Think On Axis

Selected scope: the named axis, otherwise the clearly current axis.

- Apply this scope to an operation or projection in the same request or, when invoked alone, to the next explicit one.
- Expire the selector immediately after that one use.
- Reuse the axis's stable human-readable label and preserve its relevant history and state.
- Infer the axis when context is clear; ask one question only when ambiguity would materially change the result.
- Narrow the output, not the evidence used for reasoning.
- Surface dependencies from other axes or topics when they materially change the result.

When invoked alone, reply only with `Scope set: axis “<label>” for the next operation or projection.`

Do not perform an operation by yourself or make the scope persistent.
