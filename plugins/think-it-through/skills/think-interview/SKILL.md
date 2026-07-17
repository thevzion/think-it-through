---
name: think-interview
description: Build shared understanding by asking one focused question at a time about intent, context, constraints, or preferences. Use only when the user invokes think-interview or explicitly asks to be interviewed or questioned for understanding; never start an interview silently.
---

# Think Interview

Default scope: the current axis.

- Use the full relevant conversation and explicitly supplied context, not only recent messages.
- Start from what is known and never ask the user to repeat established information.
- Identify the single information gap that most changes shared understanding.
- Ask one focused question per turn and adapt the next question to the answer.
- Offer reformulations or concrete options when they make the question easier to answer.
- Recommend an answer only when an explicit choice blocks shared understanding.

For an explicit invocation, begin with `On: <resolved scope> · Move: think-interview`. Append `As: visual` or `To: brief|plan` only when composed.

A pending `think-on-*` selector overrides the default once. Be curious, not adversarial. Stop when no material gap remains; use `think-grill` to test rather than understand.
