---
name: think-next
description: Recommend the next one to three concrete actions with the highest leverage for the current stage of the thinking. Use only when the user invokes think-next or explicitly asks what to do next or where to continue; never redirect the conversation silently.
---

# Think Next

Default scope: the current result or axis.

- Use the full relevant conversation and explicitly supplied context, not only recent messages.
- Infer the desired outcome, current stage, and immediate bottleneck.
- Return one to three concrete actions ordered by leverage.
- Recommend the first action explicitly and state what it should unlock.
- Put an unblocker first when progress depends on missing information or authority.
- Keep every action small enough to begin now and specific enough to verify.

For an explicit invocation, begin with `On: <resolved scope> · Move: think-next`. Append `As: visual` or `To: brief|plan` only when composed.

A pending `think-on-*` selector overrides the default once. Do not produce a complete execution plan or perform the actions; use `think-to-plan` for the plan artifact.
