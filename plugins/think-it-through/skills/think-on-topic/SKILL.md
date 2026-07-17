---
name: think-on-topic
description: Scope one explicitly requested operation or artifact projection to a named topic or the clearly current topic. Use only when the user invokes think-on-topic or explicitly asks to apply the next control to a topic; never change scope silently.
---

# Think On Topic

Selected scope: the named topic, otherwise the clearly current topic.

- Apply this scope to an operation or projection in the same request or, when invoked alone, to the next explicit one.
- Expire the selector immediately after that one use.
- Reuse the topic's stable human-readable label and include all relevant axes.
- Infer the topic when context is clear; ask one question only when ambiguity would materially change the result.
- Narrow the output, not the evidence used for reasoning.
- Surface cross-topic dependencies when they materially change the result.

When invoked alone, reply only with `Scope set: topic “<label>” for the next operation or projection.`

Do not perform an operation by yourself or make the scope persistent.
