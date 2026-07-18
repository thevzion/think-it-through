# Think It Through

**Write the thought. Command the next move.**

Develop your ideas with AI without losing control of the conversation.

Think It Through gives you a lightweight command palette for long, nonlinear thinking sessions. Each command gives the agent an explicit job and target, so your message can stay focused on the idea itself.

## Why it exists

You rarely form a complex idea in a clean sequence. You branch, revise an earlier assumption, introduce an unrelated thought, or return to something that mattered twenty messages ago.

Your message then starts doing two jobs: carrying the thought and explaining how the agent should handle it. You keep writing instructions such as “clarify this before answering,” “keep exploring,” or “challenge this assumption.” That conversation steering boilerplate interrupts the thought you wanted to develop.

Think It Through separates the two. Put the substance in your message. Use a short command to define the agent's job for the next turn.

## A command makes the next job explicit

~~~mermaid
flowchart LR
    H["Human thought"] --> C["Named command"]
    C --> J["Explicit job + target"]
    J --> A["Agent turn"]
    A --> N["New or clearer human thought"]
    N --> C
~~~

A named command guarantees the job, target resolution, and typed pipeline. Without a command, the agent responds normally. The command does not make generated content deterministic.

~~~text
messy thoughts     + /think-distill → clarify them, then respond
open decision      + /think-propose → give one strong direction
whole conversation + /think-recap   → recover its full shape
~~~

The agent shows how it interpreted a named command:

~~~text
On: <target> · Move: <operation>
On: <target> · Move: <operation> · With: <representation>
On: <target> · To: <artifact>
~~~

## Start with the conversational commands

These six commands cover the moments when you want to change the agent's next job:

| Command | Job |
| --- | --- |
| `/think-distill` | Clarify one or more thoughts without merging unrelated ideas, then respond |
| `/think-discuss` | Develop the current thought without forcing a conclusion |
| `/think-interview` | Build understanding through one focused question at a time |
| `/think-grill` | Test a proposal through demanding questions and recommendations |
| `/think-recap` | Recover the available conversation by topics and axes |
| `/think-propose` | Give one strong direction and its decisive tradeoff |

Most commands cover one agent turn. `/think-interview` and `/think-grill` open a multi-turn loop and retain their target until they finish or you invoke another command.

The agent does not suggest a Think It Through command unless you ask how to continue. You choose when the palette enters the conversation.

## Add precision after the basics

The rest of the palette adds session context, targets, representations, and outputs:

| Family | Commands | Job |
| --- | --- | --- |
| Session and continuation | `/think-it-through`, `/think-next` | Adopt the available conversation or choose the next useful action |
| Target | `/think-on-conversation`, `/think-on-topic`, `/think-on-axis` | Choose where the next command should focus |
| Representation | `/think-with-diagrams`, `/think-with-reasoning-map` | Add a useful visual or expose the reasoning |
| Artifact | `/think-to-brief`, `/think-to-plan` | Preserve the thinking or organize an executable direction |

Composition follows one stable pattern:

~~~text
optional target + command or artifact + optional representation
~~~

Examples:

~~~text
/think-on-axis Pricing + /think-grill
/think-recap + /think-with-diagrams
/think-on-topic Launch + /think-to-plan
~~~

The invocation is a command. `On`, `Move`, `With`, and `To` describe the dimensions the agent resolved.

## Keep the context, change the job

You can activate `/think-it-through` at any point. The agent adopts the conversation still available and maintains a quiet, best-effort map:

~~~text
Conversation
└── Topics
    └── Axes
        ├── ideas and assumptions
        ├── proposals and decisions
        ├── tensions and contradictions
        └── open questions
~~~

Each named command also reconstructs its relevant context, so the palette works without prior activation. A target narrows the job, not the evidence the agent may need.

The map tells the agent what remains in play. The command tells it what to do next.

The agent can only use material still available in the conversation or supplied by you. It cannot recover removed context or remember another chat.

## Fit the palette to your work

A command is a short name for a response you ask for often.

The included commands are a starting palette. Add one when you keep rewriting the same instruction. Merge or remove commands when they keep producing the same job.

Your practice still defines the subject, methods, and standards:

~~~text
your thought
+ a Think It Through command
+ an optional domain skill
+ an optional template
~~~

For example, an architecture skill can supply technical knowledge while `/think-grill` tests one decision. A research method can guide evidence collection while `/think-recap` reconnects the active themes. A document template can shape the artifact produced by `/think-to-brief`.

## Recap, brief, and plan

| Command | Result |
| --- | --- |
| `/think-recap` | A conversational checkpoint with a map and digest |
| `/think-to-brief` | A neutral snapshot for reuse inside or outside the session |
| `/think-to-plan` | An execution plan for an accepted or provisional direction |

A recap stays in the conversation. A brief preserves selected thinking. A plan organizes execution but never authorizes it.

## Install

This README uses portable `/think-*` notation. Codex and Claude Code load the same skills with different prefixes:

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

Grill Me supplied the seed: a short name for a response contract worth reusing. Think It Through extends that pattern into a command palette for complex thought.

- **Human creativity leads:** you provide ideas, associations, and judgment.
- **Commands stay explicit:** the agent never applies one silently.
- **Frequent use stays cheap:** each command contains one focused contract.
- **The vocabulary stays open:** repeated needs can become commands; overlapping commands can merge.

## License

MIT
