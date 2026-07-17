---
name: think-to-brief
description: Project the selected living conversation map or an explicitly co-invoked result into a neutral, standalone Thinking Brief for durable reuse. Use only when the user invokes think-to-brief or explicitly asks to materialize the thinking as a structured brief; never create or overwrite a durable artifact silently.
---

# Think To Brief

Default scope: the full available conversation map.

- Use all relevant conversation and explicitly supplied context; do not depend on an implicit recap.
- If recap is co-invoked, materialize that checkpoint instead of the living map directly.
- Structure the brief semantically as Conversation → Topics → Axes, adapted to the selected scope.
- Add purpose, audience, synthesis, cross-axis connections, decisions, tensions, open questions, and a continuation point when useful.
- Remove chat chronology and repetition while preserving uncertainty and unresolved disagreement.
- Include the smallest useful visuals; when `think-as-visual` is co-invoked, make the brief visual-first.

Before a durable write, resolve `On`, `To: brief`, optional `As`, audience, overview, outline, inclusions, exclusions, format, destination, and create/update action.

Begin the materialization brief with `On: <resolved scope> · To: brief`; append `As: visual` when applied.

If scope, audience, format, or destination is implicit, show that materialization brief and wait. Proceed directly only when the user explicitly requests direct creation with a clear destination.

Prefer an existing project convention, use portable Markdown by default, and return inline Markdown when no persistent surface exists. Never overwrite an existing destination without explicit authorization.

A pending `think-on-*` selector overrides the default once. Treat the brief as a snapshot, not a synchronized source; do not invent decisions or an execution plan.
