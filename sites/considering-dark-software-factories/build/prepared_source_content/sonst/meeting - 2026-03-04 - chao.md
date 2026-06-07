---
meadow-sensitive: true
---
### Examples

e2e test videos: [[example - screencast - videos filtered by scenario docs]]

markdown and claude code: [[example - using DeepSearch in Claude Code in a terminal in Obsidian to find a page about a software concept]]

cognitive debt: [[example - a code change that introduced cognitive debt]]

cognitive debt: [[example - obsidian spaced repetition plugin card for learning about neural networks]]

### Using AI to find and create conceptual notes

[[using AI to find or create conceptual notes]]

I shared this before, but I'm going to share it again because it's _really_ good: [[example - using DeepSearch in Claude Code in a terminal in Obsidian to find a page about a software concept]]

I'm also getting much more aggressive about using it more broadly, and a little less concerned about whether _I_ wrote the content or not.  A year ago (an eternity) I wrote [[How I use my note processing system - 2025-03]] and I fretted about whether

[[how someone might reasonably keep externally-generated notes in their notes]]

For example, I led it to write about [[type-safe specification - 2026-02]]

### We talked about since last meeting

[[t cursor video demos]]

[[t open source projects are making their test suites private to stop slop forks]]

# Dark Software Factory - DSF

**New site!** [[considering dark software factories]] (which is also an _actual_ site [here](https://www.meadow-notes.com/sites/sl4bvpb0ows5-considering-dark-software-factories-v1/considering%20dark%20software%20factories.html))

### DSF - My company creates two products... a Dark Factory and Meadow 

I've realized that my software company, Sand Harbor Software, really has _two_ products that are equally important.  [[Meadow]] and the "sand harbor" [[dark software factory]].  Why frame as a separate product?  Realistically, dark factories are on another plane than simply being an embedded feature of a single application.  Also, it's something project-agnostic that I can start talking with my engineering friends about that's not just me annoying them about Meadow.

### DSF - agent manager

```
parent tmux (agent manager)                                                
+--------------------------+----------------------------------------------+
| Agents (sidebar)         | Selected agent: meadow/feature-123           |
|--------------------------|----------------------------------------------|
| [*] agent-01 (running)   | right pane: nested tmux session (agent-01)   |
| [ ] agent-02 (idle)      | +------------------------------------------+ |
| [ ] agent-03 (error!)    | | agent tmux (inside right pane)           | |
|                          | | +--------------------------------------+ | |
| Actions                  | | | Claude Code                          | | |
|  (n) new agent           | | | (primary conversation / coding UI)   | | |
|  (r) rename              | | |                                      | | |
|  (k) kill agent          | | |                                      | | |
|  (o) open logs           | | |                                      | | |
|                          | | |                                      | | |
|                          | | +--------------------------------------+ | |
|                          | | +--------------------------------------+ | |
| Status                   | | | $ ./some-command                     | | |
|  running: 1              | | |                                      | | |
|  idle:    1              | | +--------------------------------------+ | |
|                          | +------------------------------------------+ |
+--------------------------+----------------------------------------------+
```

Written in TypeScript.  "new" creates a [[git worktree]] and a [[tmux session]] (can attach to independently)

### DSF - Wrapping agent skills

I'm creating [[agent skill]]s like crazy, in part because I'm adopting a [[agent skill wrapped scripts]] pattern, like in [[running meadow e2e tests wrapped by an agent skill]]

This pattern has caused me to become a little less excited about the [[dev_tools_app]] and my CLI tools because it's not [[agent skill wrapped]].  When something breaks, _I_ have to tell the agent to fix it.  Even if it doesn't happen very often, it's pretty annoying once you become accustomed to agents fixing things for you automatically.
:
It feels like there's some ideal combo here where _every_ command is [[agent skill wrapped]] by a dumb and fast agent that knows _just enough_ to be able to bootstrap a call to a fancier agent if something goes wrong
...
[[using a faster but dumber model with a slower but smarter model]]
...
Is _this_ what [[person - Andrej Karpathy]] meant [[t Karpathy LLMs as kernel process of a new OS]]
...
[[dim - agent-pilled amount -- more]]
...
Using [[example - using DeepSearch in Claude Code in a terminal in Obsidian to find a page about a software concept]] I had Claude write me this page [[agent skill wrapping everything is the LLM OS]]

[[dev tooling stress test]]





### Apple, tho?

[[t Apple M5 macbook has powerful AI capabilities]]

### How to do system documentation

Not sure I believe this anymore [[app specification will be done with agents and markdown]].  Given my recent work on [[scenario doc]]s, I think perhaps a [[type-safe specification - 2026-02]] might make more sense.

[[documentation skews from code]]

[[agent skill -- update-skills]]

### Evals

[[agent skill -- eval-skills]]

### AGI and ASI

[[v sam harris TED talk about AI - 2016]] 2016!  Sam just reasoned from first principles and understood we'd be where we are today... and also where we'll be tomorrow.

[[AI improvement -- recent news 26-02]]

### Coding

[[with claude remote you can interact with your code or notes from your phone, too]]

[[example - describe a desired state and have the coding agent reconcile to it]]

### Cognitive Debt

[[cognitive debt]]

[[example - a code change that introduced cognitive debt]]

[[example - obsidian spaced repetition plugin card for learning about neural networks]]


# Notes from the meeting

[[git pre-commit hook for ensuring a specific commit prefix]]

[[if you can ask 'why?' of your connected notes and get an answer, then they are not well-factored]]

New idea... [[documentation context graph may be a better place for specification info than an issue tracker]] and how it can be part of an [[agent task -- change review app]]