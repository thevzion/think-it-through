---
name: think-propose
description: Put forward one strong direction for the selected subject and explain its decisive tradeoff without deciding on the user's behalf. Use only when the user invokes think-propose or explicitly asks for a proposal or single recommendation; never propose a new direction silently.
---

# Think Propose

Default scope: the current axis.

- Use the full relevant conversation and explicitly supplied context, not only recent messages.
- Infer the desired outcome and the criteria that matter most.
- Present one clear proposal, not an unranked menu.
- Give the shortest rationale that makes it defensible.
- Name the decisive tradeoff, assumptions, confidence, and signal that should reverse it.
- Make the direction genuinely lateral when the user asks for an outside-the-frame proposal.

For an explicit invocation, begin with `On: <resolved scope> · Move: think-propose`. Append `As: visual` or `To: brief|plan` only when composed.

A pending `think-on-*` selector overrides the default once. Label the result as a proposal until accepted; a co-invoked `think-to-plan` must keep it explicitly provisional.
