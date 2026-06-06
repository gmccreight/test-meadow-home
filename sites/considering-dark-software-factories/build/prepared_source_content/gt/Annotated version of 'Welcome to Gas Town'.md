Here is the original blog post https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04 by [[person - Steve Yegge]]

# Annotated quotes from the post

*The annotations work like this.  If I can replace a concept directly inline in the quote with a link, I do that.  If not, I add an annotation with further details afterwards.*

### [[Blog Post -- Section 1 - What the heck is Gas Town?|Section 1 - What the heck is Gas Town?]]

[[spaced repetition prompts - blog section 1 - What the heck is Gas Town?|spaced repetition cards]]

But it works! Gas Town solves [[p Solving a Million-Step LLM Task with Zero Errors]] (20-disc Hanoi towers) trivially with a million-step wisp you can generate from a formula. I ran the 10-disc one last night for fun in a few minutes, just to prove a thousand steps was no issue (MAKER paper says LLMs fail after a few hundred).
...
I mention [[performance benchmark -- Towers of Hanoi]] in [[examples of excellent state validations]]

[[Steve Yegge's AI adoption Chart]]

### [[Blog Post -- Section 2 - Gas Town Was No Secret|Section 2 - Gas Town Was No Secret]]

[[spaced repetition prompts - blog section 2 - Gas Town Was No Secret|spaced repetition cards]]

It will have to have multiple levels of agents supervising other agents,” I said.

“It will have a [[code merge queue|Merge Queue]],” I said.
:
“It will [[agent workflow orchestration|orchestrate workflows ]],” I said.
:
“It will have plugins and [[quality gate]]s,” I said.

### [[Blog Post -- Section 3 - WARNING DANGER CAUTION|Section 3 - WARNING DANGER CAUTION]]

[[spaced repetition prompts - blog section 3 - WARNING DANGER CAUTION|spaced repetition cards]]

Gas Town is designed to scale up in three dimensions this year with (1) model cognition, (2) agents becoming more Gas Town-friendly, and(3) Gas Town and Beads making it into the training corpus for frontier models Even without all that, it’s already shocking that the agents use Beads and Gas Town so effortlessly. With zero training.

One thing to know up front about Gas Town: it degrades gracefully. Every worker can do their job independently, or in little groups, and at any time you can choose which parts of Gas Town you want running. It even works in no “no-tmux” mode, and limps along using naked Claude Code sessions without real-time messages. It’s a little slower, but it still works.
...
[[graceful system degradation]] [[Cross agent messaging]]

Gas Town’s propulsion ([[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]]) is effective, but still a bit flaky right now, and sometimes you will need to go hustle the [[Term -- Polecats|Polecats]]s to get their [[Term -- Merge Request - MR|MR]] submitted, and then hustle the Refinery to deal with them. The Witness patrol helps smooth this out so it’s almost perfect for most runs.
...
Pushing along the [[worker agent]]s and the [[specialized agent -- code merge]]

### [[Blog Post -- Section 4 - Gas Town 101|Section 4 - Gas Town 101]]

[[spaced repetition prompts - blog section 4 - Gas Town 101|spaced repetition cards]]


![[Term -- The Town]]


![[Term -- Rigs]]


![[Term -- The Overseer]]


![[Term -- The Mayor]]


![[Term -- Polecats]]


![[Term -- Refinery]]


![[Term -- The Witness]]


![[Term -- The Deacon]]


![[Term -- Dogs]]


![[Term -- Boot the Dog]]


![[Term -- The Crew]]

![[Term -- Patrol]]



All rig-level workers (refinery, witness, polecats and crew) are perfectly able to work cross-rig when they need to. There is a `gt worktree` command that they can use to grab their own clone of any rig and make a fix. But normally they work inside a single project.
...
[[Role Class -- Worker -- Rig Level]]

### [[Blog Post -- Section 5 - A Note About Mad Max Theming|Section 5 - A Note About Mad Max Theming]]

No notes.  Makes sense!

### [[Blog Post -- Section 6 - Gastown Universal Propulsion Principle|Section 6 - Gastown Universal Propulsion Principle]]

[[spaced repetition prompts - blog section 6 - Gastown Universal Propulsion Principle|spaced repetition cards]]

All Gas Town workers, in all roles, have persistent identities in [[project - Beads]], which means in Git. A worker’s [[Term -- Identity Type|identity type]] is represented by a [[Term -- Role Bead|Role Bead]], which is like a domain table describing the role. And each worker has an [[Term -- Agent Bead|Agent Bead]], which is the agent’s persistent identity.
...
[[Role Class -- Worker]]

Both [[Term -- Role Bead|Role Bead]]s and [[Term -- Agent Bead|Agent Bead]]s (as well as [[Term -- Hook|Hook]]s) are examples of [[Term -- Pinned Bead|Pinned Bead]]s”, meaning they float like yellow-sticky notes in the Beads data plane, and never get closed like regular issues (unless the identity goes away). They don’t show up in `bd ready` (ready work) and they’re treated specially in various other ways.

In Gas Town, an [[Term -- Agent|Agent]] is not a session. [[Term -- Session|Session]]s are ephemeral; they are the “cattle” in the Kubernetes [[pets vs cattle]] metaphor. Claude Code sessions are the cattle that Gas Town throws at persistent work. That work all lives in [[project - Beads|Beads]], along with the persistent identities of the workers, and the [[Term -- Town Mail|Town Mail]], the event system, and even the ephemeral orchestration, as we will see.

In Gas Town, [[principle - an agent is a Bead|an agent is a Bead]], an identity with a singleton global address. It has some slots, including a pointer to its [[Term -- Role Bead|Role Bead]] (which has priming information etc. for that role), its mail inbox (all Beads), its [[gt/Term -- Hook|Hook]] (also a Bead, used for [[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]]), and some administrative stuff like orchestration state (labels and notes). The history of everything that agent has done is captured in Git, and in Beads.

So what is a [[Term -- Hook|Hook]]? Every Gas Town [[Term -- Worker|Worker]] has its own hook 🪝. It’s a special [[Term -- Pinned Bead|Pinned Bead]], just for that agent, and it’s where you hang [[Term -- Molecule|Molecule]]s, which are Gas Town workflows.

One of the simplest but greatest things about Gas Town is that any time in any session, you can say, “let’s hand off”, and the worker will gracefully clean up and restart itself. Thanks to GUPP, the agent will continue working automatically if it’s hooked.
...
[[Term -- handoff|handoff]]
...
[[system property - resilient to failures]]

Unfortunately, Claude Code is so miserably *polite* that GUPP doesn’t always work in practice. We tell the agent, YOU MUST RUN YOUR HOOK, and it sometimes doesn’t do anything at all. It just sits there waiting for user input.
...
[[agent problem - Claude Code is polite and waits for user input]]


### [[Blog Post -- Section 7 - The GUPP Nudge|Section 7 - The GUPP Nudge]]

[[spaced repetition prompts - blog section 7 - The GUPP Nudge|spaced repetition cards]]


### [[Blog Post -- Section 8 - Talking to your Dead Ancestors|Section 8 - Talking to your Dead Ancestors]]

[[spaced repetition prompts - blog section 8 - Talking to your Dead Ancestors|spaced repetition cards]]

This is useful because often, a worker will say, “OK, I handed off this big pile of work and advice to my successor! Kbai! `/handoff` ”, and disappear, and then the new worker will spin up and be like, “What? I don’t see shit.” You used to have to clumsily go figure out which session was the previous one, out of your last 40-odd sessions, all of which start with “let’s go”, because you have been doing the GUPP nudge manually. It was really awkward and almost not worth it.
...
[[agent problem - sometimes agents don't tie up their work properly at the end]]


### [[Blog Post -- Section 9 - Molecular Expression of Work (MEOW)|Section 9 - Molecular Expression of Work (MEOW)]]

[[spaced repetition prompts - blog section 9 - Molecular Expression of Work (MEOW)|spaced repetition cards]]

If the workflow is captured as a molecule, then it survives agent crashes, compactions, restarts, and interruptions. Just start the agent up in the same sandbox, have it find its place in the molecule, and pick up where it left off.
...
[[molecules lead to resilience]]


### [[Blog Post -- Section 10 - Nondeterministic Idempotence|Section 10 - Nondeterministic Idempotence]]

[[spaced repetition prompts - blog section 10 - Nondeterministic Idempotence|spaced repetition cards]]

Because AIs are really good at following TODO lists and acceptance criteria, they are reliable at following molecules. They get the idea of GUPP, and they understand that the bureaucracy of checking off issues, no matter how trivial, updates a live activity feed and puts the work on a permanent ledger. That reasoning is enough to keep them humming along and on-track while they do it. They don’t get “bored”, and they are far less likely to make mistakes because they are not managing their own TODO list (except within a single, small step).
...
[[agent problem - worker agents are flaky and need management]], but they get less flaky when they have one job and a manager.  Same observation as the [[Ralph loop]].

So it doesn’t matter if Claude Code crashes, or runs out of context. As soon as another session starts up for this agent role, it will start working on that step in the molecule immediately (via GUPP, or when it gets nudged by one of the [[Term -- Patrol|Patrol]] agents). If it finds out that it crashed in the middle of the last step, no biggie, it will figure out the right fix, perform it, and move on.
...
[[system property - resilient to failures]]


### [[Blog Post -- Section 11 - Wisps - Ephemeral Orchestration Beads|Section 11 - Wisps - Ephemeral Orchestration Beads]]

[[spaced repetition prompts - blog section 11 - Wisps - Ephemeral Orchestration Beads|spaced repetition cards]]


### [[Blog Post -- Section 12 - Patrols|Section 12 - Patrols]]

[[spaced repetition prompts - blog section 12 - Patrols|spaced repetition cards]]


### [[Blog Post -- Section 13 - Gas Town Plugins|Section 13 - Gas Town Plugins]]

[[spaced repetition prompts - blog section 13 - Gas Town Plugins|spaced repetition cards]]


### [[Blog Post -- Section 14 - Convoys|Section 14 - Convoys]]

[[spaced repetition prompts - blog section 14 - Convoys|spaced repetition cards]]

Real example: I often tell my Beads crew to sling the release molecule to a polecat. The polecat will walk through the 20-step release process, finish it off, and then I’ll be notified that the Convoy has landed/finished. *Edit: Actually it’s even fancier, now. The polecat disappears while the molecule is waiting in [[Term -- Gate state|Gate state]]s, such as awaiting a GH Action or CI/CD. And then when the [[Term -- Gate bead|Gate bead]] triggers, Gas Town wakes up a polecat to continue the work.*


### [[Blog Post -- Section 15 - Gas Town Workflow|Section 15 - Gas Town Workflow]]

[[spaced repetition prompts - blog section 15 - Gas Town Workflow|spaced repetition cards]]


### [[Blog Post -- Section 16 - Planning in Gas Town|Section 16 - Planning in Gas Town]]

[[spaced repetition prompts - blog section 16 - Planning in Gas Town|spaced repetition cards]]

I implemented a [[Term -- Formula|Formula]] for Jeffrey Emanuel’s [[Rule of Five]] which is the observation that if you make an LLM review something five times, with different focus areas each time though, it generates superior outcomes and artifacts. So you can take any workflow, cook it with the Rule of Five, and it will make each step get reviewed 4 times (the implementation counts as the first review).


### [[Blog Post -- Section 17 - Comparison to Kubernetes|Section 17 - Comparison to Kubernetes]]

[[spaced repetition prompts - blog section 17 - Comparison to Kubernetes|spaced repetition cards]]

Gas Town does maybe look a bit like Kubernetes, unintentionally. Both systems coordinate unreliable workers toward a goal. Both have a control plane (Mayor/Deacon vs kube-scheduler/controller-manager) watching over execution nodes (Rigs vs Nodes), each with a local agent (Witness vs kubelet) monitoring ephemeral workers (Polecats vs Pods). Both use a source of truth (Beads vs etcd) that the whole system reconciles against. These are apparently the natural shapes that emerge when you need to herd cats at scale.
...
[[dim - resilience -- higher]]