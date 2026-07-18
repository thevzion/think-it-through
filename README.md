# Think It Through

**Think out loud. Keep the threads connected.**

A toolkit for brainstorming and developing complex ideas with AI across long conversations.

Write fragments as they come. Use lightweight, composable controls to shape how the agent helps you clarify, explore, challenge, reconnect, or preserve them.

## Why it exists

Your ideas can arrive faster than you can package them into prompts. Each time you want a different kind of help, you stop thinking and explain how the agent should respond: clarify this, keep exploring, recover earlier threads, or challenge this assumption.

Think It Through turns those repeated steering instructions into lightweight controls. Write the thought, invoke a move, and keep going.

Developers may recognize this repetition as **conversation steering boilerplate**. It grows during nonlinear work because your needs change from one message to the next. You may want room to explore now, a recap two messages later, then a hard challenge on one branch.

Long sessions add another problem. Earlier constraints get buried, your assumptions change, and the agent can over-focus on recent messages. Think It Through asks the agent to reconstruct the relevant conversation before each explicit control.

## See it in one conversation

This shortened example comes from the conversation that designed the kit.

**Human**

> I think this may be a kit rather than a methodology. The commands remove the instructions I keep repeating, but I also want the agent to recover an idea from much earlier. Maybe those are separate promises? And the agent's replies can trigger more ideas in the human.

~~~text
/think-distill + /think-discuss
~~~

**Agent**

~~~text
On: latest human message · Move: think-distill → think-discuss

Distilled:
- The product may be a reusable kit rather than a fixed methodology.
- Its controls remove repeated steering instructions.
- It should reconnect earlier ideas during long conversations.
- Agent responses can give the human new material to think with.

Together, these points describe a kit that supports a feedback loop without
prescribing the subject or the order of work...
~~~

The response gives the human another thought.

**Human**

> Then the controls could form a workflow specific to each subject. A product discussion and a research project would use the same verbs in different orders.

~~~text
/think-discuss
~~~

After more branches appear:

~~~text
/think-recap
~~~

The recap reconstructs the conversation by topics and axes instead of summarizing the latest exchange. The human can then target one fragile branch:

~~~text
/think-on-axis Product category + /think-grill
~~~

~~~text
Recommendation: lead with the human problem before naming the product category.

Question: which sentence would make someone recognize their own long,
branching conversation before they learn the kit's vocabulary?
~~~

One invocation keeps the grill active across the user's answers. When the direction becomes clear, the human can request one proposal and preserve the result:

~~~text
/think-propose
/think-to-brief
~~~

The human selected each move as the conversation changed. No fixed workflow prescribed the sequence.

## Made for repeated use

Many skills execute a bounded task. You use Think It Through controls while the conversation unfolds. Invoke one once, repeat it across several turns, or switch controls as your thinking changes.

The included skills are a starter vocabulary. They are small enough to use once, several turns in a row, or whenever the conversation needs a different kind of help.

| Controls | Cadence |
| --- | --- |
| `think-distill`, `think-discuss`, `think-recap`, `think-propose`, `think-next` | Invoke whenever that conversational need appears |
| `think-interview`, `think-grill` | Invoke once to start a multi-turn loop |
| `think-on-*`, `think-with-*` | Apply once to the next or current result |
| `think-to-*` | Use when you want a checkpoint or operational output |
| `think-it-through` | Activate when a conversation becomes worth tracking |

Every control remains explicit. The agent may suggest one, but it never applies one without your request. The agent reconstructs relevant context for every explicit control, so moves also work without prior activation of `/think-it-through`.

## How it works

Your ideas direct the exchange. The agent returns connections, questions, and possible directions. Your reaction gives the next response richer context.

~~~mermaid
flowchart LR
    H["Human thought"] --> M["Explicit move"]
    M --> A["Agent response"]
    A --> N["New or clearer human idea"]
    N --> M
~~~

When you activate `/think-it-through`, the agent adopts the conversation still available and maintains a best-effort map:

~~~text
Conversation
└── Topics
    └── Axes
        ├── ideas and assumptions
        ├── proposals and decisions
        ├── tensions and contradictions
        └── open questions
~~~

A topic is a broad subject. An axis is a stable, human-readable branch within it. Axes may stay active, pause, resolve, or be replaced.

A selected target never discards the rest of the context. For example, `/think-on-axis Positioning + /think-grill` centers the grill on Positioning while retaining dependencies from the rest of the conversation.

## The included vocabulary

Start with the controls that match common moments:

| Control | Use it when |
| --- | --- |
| `/think-distill` | Your message contains fragments, implicit meaning, or several thoughts that need clearer wording |
| `/think-discuss` | You want to develop the current thought without forcing a conclusion |
| `/think-recap` | You need the full shape of the available conversation |
| `/think-grill` | You want to test a proposal or assumption across a multi-turn interview |
| `/think-propose` | You want one strong direction and its decisive tradeoff |
| `/think-to-brief` | You want to preserve the thinking as a reusable brief |

The complete kit follows four naming families:

| Family | Controls | Purpose |
| --- | --- | --- |
| Session and moves | `/think-it-through`, `/think-distill`, `/think-discuss`, `/think-interview`, `/think-grill`, `/think-recap`, `/think-propose`, `/think-next` | Adopt, clarify, explore, understand, test, reconnect, orient, or continue |
| Target | `/think-on-conversation`, `/think-on-topic`, `/think-on-axis` | Select where the next control should focus |
| Representation | `/think-with-diagrams`, `/think-with-reasoning-map` | Add a useful visual or expose the reasoning |
| Artifact | `/think-to-brief`, `/think-to-plan` | Preserve the thinking or organize an executable direction |

The grammar stays stable:

~~~text
optional target + move or artifact + optional representation
~~~

Examples:

~~~text
/think-recap + /think-with-diagrams
/think-on-topic Product + /think-propose + /think-with-reasoning-map
/think-on-axis Deployment + /think-to-plan
~~~

You can use natural-language requests too. The names provide short handles and shared vocabulary.

## Fits the way you already work

Think It Through shapes the conversation, not the subject. Your existing practice still defines the methods, criteria, and output.

~~~text
your practice
+ a Think It Through control
+ an optional domain skill
+ an optional template or artifact
~~~

A technical architecture skill can supply domain knowledge while `/think-grill` tests one decision. A research method can guide evidence collection while `/think-recap` reconnects the active themes. A document template can shape the Thinking Brief without changing the conversation that produced it.

Teams can add controls when repeated use reveals a distinct conversational effect. The compositional grammar does not need to change.

## Recap, brief, and plan

These controls preserve different amounts of commitment:

| Result | Purpose | Persistence |
| --- | --- | --- |
| `/think-recap` | Recover the available map and give a coherent digest | Conversation only |
| `/think-to-brief` | Preserve selected thinking without adding a direction | Inline Markdown or an approved destination |
| `/think-to-plan` | Organize an accepted or provisional executable direction | Native plan or an approved destination |

The agent can only use conversation and material still available to it. It cannot recover details removed from context or remember another chat. Use recap as a checkpoint while thinking. Use a brief when the result needs to survive the session.

A plan does not authorize implementation. The agent waits for approval.

## Install and invoke

This README uses portable `/think-*` notation. Codex and Claude Code load the same `SKILL.md` files with different prefixes:

| Portable | Codex | Claude Code |
| --- | --- | --- |
| `/think-recap` | `$think-it-through:think-recap` | `/think-it-through:think-recap` |

### Codex

~~~bash
codex plugin marketplace add thevzion/think-it-through
codex plugin add think-it-through@think-it-through
~~~

### Claude Code

~~~bash
claude plugin marketplace add thevzion/think-it-through --scope user
claude plugin install think-it-through@think-it-through --scope user
~~~

## Origin and principles

Grill Me supplied the seed: one short name for a precise, reusable conversation contract. Think It Through applies that pattern to more moments in complex thought.

- **Human-led:** you own the intent, direction, and judgment.
- **Frequent by design:** short contracts keep repeated use cheap.
- **No hidden workflow:** the agent applies controls only when you ask.
- **Context-aware:** a narrow target retains relevant history and dependencies.
- **Open vocabulary:** new controls must earn their place through a distinct repeated effect.

## License

MIT
