---
name: think-distill
description: Clarify the intended meaning of the user's latest fragmented, implicit, or hard-to-word message, then respond to that clarified thought or pass it to a co-invoked operation. Use only when the user invokes think-distill or explicitly asks for their thought to be clarified before answering; never rewrite their meaning silently.
---

# Think Distill

Default scope: the latest user message interpreted within the current axis.

- Use the full relevant conversation and explicitly supplied context to interpret the message.
- Identify the intended meaning, distinct ideas, implicit assumptions, tensions, and material ambiguity.
- Present the shortest faithful formulation under `Distilled`.
- Preserve uncertainty and the user's voice; do not make the thought more settled than it is.
- Under `Response`, answer the clarified thought as a neutral thinking partner.
- When another operation is co-invoked, apply it to the distilled formulation instead of adding a neutral response.
- Ask one question only when plausible interpretations would materially change the answer.

For an explicit invocation, begin with `On: <resolved scope> · Move: think-distill`; show a co-invoked operation as `think-distill → <operation>`.

A pending `think-on-*` selector overrides the interpretive scope once. Do not turn every rough message into heavy structure or polish away meaningful ambiguity.
