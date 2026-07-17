# Think It Through

**Think freely. The agent keeps the map.**

Think It Through is a lightweight system for extracting, mapping, and advancing complex thought with AI.

You do not need to think linearly for the agent. Drop ideas as they come—unfinished, branching, or contradictory. The agent turns the available conversation into a living map, keeps earlier threads connected, and applies one explicit operation at a time when you want to clarify, explore, challenge, synthesize, propose, or produce a reusable artifact.

The human remains the author and driver. The agent acts as a working memory and cartographer without silently taking the conversation in a new direction.

## Why it exists

Human thought is divergent. We circle back, open side paths, contradict ourselves, and discover the importance of an earlier idea much later.

AI conversations can flatten that process into the latest few messages. Early assumptions disappear, related branches drift apart, and summaries follow chronology instead of meaning.

Think It Through gives the agent a simple job:

1. Let the human think nonlinearly.
2. Maintain a coherent map of the available conversation.
3. Apply only the operation the human requests.
4. Reflect the map in conversation or project it into a reusable artifact.

It is useful for product and technical design, strategy, research, writing, personal projects, and any subject too connected or uncertain for a single prompt.

## The system

~~~mermaid
flowchart LR
    H["Raw human thought<br/>unfinished · nonlinear · contradictory"]
    D["Distill<br/>make the intended meaning explicit"]
    M["Living map<br/>Conversation → Topics → Axes"]
    O["Conversational operations<br/>discuss · interview · grill<br/>recap · propose · next"]
    B["Thinking Brief<br/>neutral reusable artifact"]
    P["Execution Plan<br/>operational artifact"]
    S["Scope<br/>on-conversation · on-topic · on-axis"]
    V["Representation<br/>as-visual"]

    H --> D
    D --> M
    M --> O
    O --> M
    M --> B
    M --> P
    O --> B
    S -.-> M
    V -.-> O
    V -.-> B
    V -.-> P
~~~

The conversation is the live workspace. Operations change what the agent does inside it. Artifact projections turn selected thinking into something designed to survive outside it.

## The living map

~~~text
Conversation
└── Topics
    └── Axes
        ├── ideas and assumptions
        ├── proposals and decisions
        ├── tensions and contradictions
        └── open questions
~~~

- A **conversation** is the current chat plus any context or checkpoints explicitly provided.
- A **topic** is a broad subject being explored.
- An **axis** is a stable, human-readable branch of a topic.
- An **operation** transforms or reflects selected thinking.
- A **representation** changes how a result is shown without changing its substance.
- An **artifact** is a standalone projection made for reuse.

Axes may be active, paused, resolved, or superseded. The agent quietly reuses stable labels and reconnects later insights to earlier axes when they materially affect the discussion.

Think It Through does not promise memory across separate conversations. Briefs and other explicitly supplied artifacts are how durable context travels.

## A typed command grammar

The command families answer different questions:

| Family | Meaning | Examples |
| --- | --- | --- |
| `/think-*` | What conversational operation should happen? | `/think-discuss`, `/think-recap` |
| `/think-on-*` | Which part of the map should it use? | `/think-on-topic`, `/think-on-axis` |
| `/think-as-*` | How should the result be represented? | `/think-as-visual` |
| `/think-to-*` | What reusable artifact should be produced? | `/think-to-brief`, `/think-to-plan` |

They compose without becoming a workflow engine:

~~~text
/think-distill + /think-propose
/think-on-topic Product + /think-recap + /think-as-visual
/think-on-conversation + /think-to-brief
/think-recap + /think-to-brief
/think-on-topic v0.3 + /think-to-plan + /think-as-visual
~~~

The order shown above is canonical notation, not a parser requirement. There is no mandatory sequence.

## Progressive transparency

The map stays silent during ordinary conversation. An explicitly requested operation begins with a compact resolved line:

~~~text
On: axis “Audience” · Move: think-interview
~~~

Representation and artifact projections appear only when applied:

~~~text
On: topic “Product” · Move: think-recap · As: visual
On: conversation · To: brief
~~~

A selector invoked alone only confirms the pending scope for the next explicit operation or projection.

## Operations

| Operation | Effect | Default |
| --- | --- | --- |
| `/think-it-through` | Open or resume a topic and establish its intent and first axes. | Supplied topic, otherwise current topic |
| `/think-distill` | Clarify the latest message, then respond or pass it to a co-invoked operation. | Latest message in the current axis |
| `/think-discuss` | Explore and connect without forcing closure. | Current axis |
| `/think-interview` | Build shared understanding with one focused question at a time. | Current axis |
| `/think-grill` | Stress-test assumptions, evidence, tradeoffs, and failure modes. | Current axis or specific current object |
| `/think-recap` | Show the selected map, then its coherent digest. | Current topic |
| `/think-propose` | Put forward one strong direction without deciding for the human. | Current axis |
| `/think-next` | Recommend the next one to three highest-leverage actions. | Current result or axis |

`/think-interview` tries to understand. `/think-grill` tries to find what does not hold. `/think-propose` can be made lateral or unconventional through the request.

## Scope

| Selector | Effect |
| --- | --- |
| `/think-on-conversation` | Apply one operation or projection to the whole available conversation. |
| `/think-on-topic` | Apply one operation or projection to a named or inferred topic. |
| `/think-on-axis` | Apply one operation or projection to a named or inferred axis. |

A selector applies to the same request or, when used alone, to the next explicit operation or projection. It expires immediately afterward.

Scope narrows the output, not the evidence used for reasoning. Material dependencies outside the selected scope remain visible.

## Representation

`/think-as-visual` preserves the selected operation or artifact and makes its representation visual-first.

It chooses the smallest useful form: a table for mappings, a flow for sequence, a tree for branching, a timeline for change, a matrix for tradeoffs, or Mermaid for relationships.

Used alone, it visualizes a recap of the current axis. Briefs and plans may include useful visuals by default; `/think-as-visual` makes that emphasis explicit.

## Recap and artifacts

| Result | Purpose | Default surface | Persistence |
| --- | --- | --- | --- |
| `/think-recap` | Reflect the current map so the conversation can continue. | Conversation | None |
| `/think-to-brief` | Preserve selected understanding as a neutral Thinking Brief. | Confirmed artifact destination | Explicit snapshot |
| `/think-to-plan` | Operationalize an accepted or explicitly provisional direction. | Native planning surface or conversation | Optional after approval |

Recap is conversational. A Thinking Brief and an Execution Plan are artifacts. Neither artifact is an implicit recap.

An explicit composition such as `/think-recap + /think-to-brief` materializes that checkpoint rather than the living map directly.

## Thinking Briefs

`/think-to-brief` reads the selected living map directly. Its default scope is the full conversation.

A brief follows the map semantically without forcing a rigid template:

~~~text
Title, purpose, audience, and status
Executive synthesis

Topic A
├── Axis A1
└── Axis A2

Topic B
└── Axis B1

Cross-topic connections
Decisions and proposals
Tensions and open questions
Continuation point
~~~

A product spec, design document, strategy brief, research brief, or decision note is a contextual shape of the same neutral artifact—not a separate skill.

Before a durable write, the agent resolves the full projection:

~~~text
On: conversation · To: brief

Artifact: Think It Through product brief
Purpose: Preserve the current product model for reuse
Audience: Maintainers and future agents
Overview: One-paragraph description of the resulting document
Outline: Topics, axes, synthesis, decisions, and open questions
Include: Established reasoning and material uncertainty
Exclude: Chat chronology and repetition
Format: Portable Markdown
Destination: docs/think-it-through-brief.md
Action: Create
~~~

When scope, audience, format, or destination remains implicit, this materialization brief waits for confirmation. A request that explicitly asks for direct creation with a clear destination may proceed immediately. Existing destinations are never overwritten without explicit authorization.

The agent prefers an established project convention. Without a persistent surface, it returns portable Markdown inline. A Thinking Brief is a snapshot, not an automatically synchronized source.

## Execution Plans

`/think-to-plan` projects the current accepted or explicitly provisional direction into an ordered, verifiable execution plan.

It uses the whole relevant map for constraints but plans only the selected direction. Without an identifiable execution intent, it asks one focused question instead of manufacturing a plan.

The agent uses its native planning surface when one exists. Otherwise it returns a proposed plan inline. The human validates the plan before implementation.

After approval, the plan may be written to an explicitly selected persistent destination before execution. Without such a destination, it remains in the native planning surface or conversation. Planning never authorizes implementation.

## Examples

### Product and technical design

~~~text
/think-it-through Should this API be a library or a managed service?
/think-grill
/think-on-topic Architecture + /think-recap + /think-as-visual
/think-to-brief
~~~

### Strategy or a personal project

~~~text
/think-it-through How should I turn this side project into a sustainable practice?
/think-distill + /think-discuss
/think-on-axis Time and energy + /think-interview
/think-propose
/think-to-plan
~~~

### Research or creative work

~~~text
/think-it-through What is the central argument of this essay?
/think-discuss
/think-on-conversation + /think-recap
/think-to-brief Research brief
~~~

## From Grill Me to a thinking system

Think It Through grew from a simple observation: Grill Me worked because it was not a topic-specific prompt. It was a reusable conversation operation—a short name for a precise interaction contract.

Think It Through extends that principle beyond pressure-testing. `think-grill` remains the demanding challenge operation; the rest of the system clarifies, explores, maps, reflects, proposes, represents, and projects the thinking around it.

**Grill Me was the seed. Think It Through is the system around it.**

## Install and invoke

The README uses canonical `/think-*` notation so the method has one portable language. Clients expose that language differently:

| Canonical operation | Codex | Claude Code |
| --- | --- | --- |
| `/think-recap` | `$think-it-through:think-recap` | `/think-it-through:think-recap` |

### Codex

~~~bash
codex plugin marketplace add thevzion/think-it-through
codex plugin add think-it-through@think-it-through
~~~

For example, invoke `$think-it-through:think-to-brief`.

### Claude Code

~~~bash
claude plugin marketplace add thevzion/think-it-through --scope user
claude plugin install think-it-through@think-it-through --scope user
~~~

For example, invoke `/think-it-through:think-to-brief`.

The same `SKILL.md` files power both integrations. Provider manifests are packaging, not separate implementations.

Explicit natural-language requests work too. Slash names are the short handles and canonical notation used throughout this README.

## Philosophy

- **Human-led.** The agent may suggest an operation but never applies a directional one silently.
- **Silent map.** Structure supports ordinary conversation instead of interrupting it.
- **Progressive transparency.** Explicit controls reveal their resolved scope and effect.
- **Syntax-optional.** Commands are handles, not a language the human must learn.
- **One operation, one effect.** Overlapping behavior is merged or removed.
- **Standalone and composable.** Every skill has useful defaults and can combine without hidden modes.
- **Lightweight.** Precise wording does the work; every skill stays inspectable at a glance.

## Repository

~~~text
.agents/plugins/marketplace.json
.claude-plugin/marketplace.json
plugins/think-it-through/
├── .codex-plugin/plugin.json
├── .claude-plugin/plugin.json
└── skills/
    └── <operation>/SKILL.md
~~~

There is no build step, generated copy, dependency, hook, MCP server, or runtime.

The method evolves from real conversations. Tighten vague operations, remove redundant ones, and add a new projection only when repeated use reveals a distinct outcome.

## License

MIT
