---
name: think-on-conversation
description: Scope one explicitly requested operation or artifact projection to the entire current chat plus any context or checkpoints the user supplied. Use only when the user invokes think-on-conversation or explicitly asks to apply the next control across the whole conversation; never change scope silently.
---

# Think On Conversation

Selected scope: the full available conversation.

- Apply this scope to an operation or projection in the same request or, when invoked alone, to the next explicit one.
- Expire the selector immediately after that one use.
- Include every relevant topic and axis from the current chat and explicitly supplied context.
- Narrow the output, not the evidence used for reasoning.
- Surface dependencies outside the apparent scope when they materially change the result.

When invoked alone, reply only with `Scope set: conversation for the next operation or projection.`

Do not perform an operation by yourself or imply memory across separate chats.
