---
name: think-distill
description: Clarify one or more thoughts in the user's latest fragmented, implicit, or hard-to-word message without merging distinct ideas, then respond or pass the result to a co-invoked control. Use only when the user invokes think-distill or explicitly asks for clarification before answering; never activate it silently.
---

# Think Distill

Context: the full relevant conversation and explicitly supplied material.

Default target: the latest human message, interpreted in its context.

- Reconstruct the context that changes the meaning of each material thought.
- Infer intended claims, questions, tensions, or connections while preserving real ambiguity and the user's voice.
- Keep unrelated or distant thoughts separate. Create a connection only when the message or its context supports one.
- Show `Distilled:` followed by one clear formulation for a single thought or a short list for several thoughts.
- Keep new implications, advice, and improved claims in the response, outside the distilled formulation.
- When used alone, respond to the distilled thought or list in the same structure.
- When another move or projection is co-invoked, pass it the distilled result instead of answering twice.
- If two materially different readings remain, show both and ask one discriminating question.
- Do not turn clarification into a recap, challenge, proposal, or plan unless explicitly composed.

For an explicit invocation, begin with:

`On: <resolved target> · Move: think-distill`

Add co-invoked `Move`, `To`, or `With` controls to the same pipeline line. A `think-on-*` selector overrides the target once, then expires; it never narrows relevant context. Never apply another control silently.
