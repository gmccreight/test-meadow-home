^ review - [[b OpenAI harness engineering 2026-02]] - 2026-02-22

---

Notes:

* [[b OpenAI harness engineering 2026-02]]
* [[free recall - Open AI harness blog post - 2026-02]]
* this review (three days after that free recall)
* [[to remove - Agentic engineering practices - scorecard 2026-04]] (throughout)

---

I will re-read [[b OpenAI harness engineering 2026-02]] and make notes about what I marked [[cannot recall]] in my earlier [[free recall - Open AI harness blog post - 2026-02]] session.  Also, I'll make note of any other areas that I think I may have missed.

---

### Gaps

* I was unclear on what "enforceability" meant.  I now think it means being able to run the gamut of [[validation script]]s that are applied at every [[SDLC building block]]
	* These validation scripts run as [[practice - background check]]s
	* Could be similar to [[behavioral guardrail]]s?
* They put a lot of effort into automating their [[code review]], including it basically having its own [[project - ralph wiggum]] loop.
* It's not just [[no human -- coding]], [[no human -- code review]], and [[no human -- app verification]].  Within things like coding, it's about not needing to give _any_ feedback.  You shouldn't have to tell it "hey, you forgot a unit test... please add and TDD".  That's far too involved, even if you aren't directly writing the code.  Instead you need to try force that into the automated process.  This is [[fix the harness so that it fixes the code]].  This feels like [[Kent Beck thought about what he did and distilled principles and practices into the Extreme Programming book]], but these guys are doing it for agents, instead
* [[The onboarding a new teammate lens to agent context engineering]].  A [[Moc framing]]


### Detailed Reading Notes


One noteworthy thing is that this is internal users only (and external alpha testers) but not real users.

To do that, we needed to understand what changes when a software engineering team’s primary job is no longer to write code, but to design environments, specify intent, and build feedback loops that allow Codex agents to do reliable work.
...
Emphasis on [[designing environments]] and building [[feedback loop]]s

Even the initial AGENTS.md file that directs agents how to work in the repository was itself written by Codex.

This translates to an average throughput of 3.5 PRs per engineer per day, and surprisingly the throughput has _increased_ as the team has grown to now seven engineers. Importantly, this wasn’t output for output’s sake: the product has been used by hundreds of users internally, including daily internal power users.
...
The team velocity increased over time and as more developers were added.  Basically the opposite of the [[book - mythical man month]].

The lack of hands-on human coding **introduced a different kind of engineering work, focused on systems, scaffolding, and leverage**.
...
I feel like leverage and [[feedback loop]]s are related

In practice, this meant working depth-first: breaking down larger goals into smaller building blocks (design, code, review, test, etc), prompting the agent to construct those blocks, and using them to unlock more complex tasks. When something failed, the fix was almost never “try harder.” Because the only way to make progress was to get Codex to do the work, human engineers always stepped into the task and asked: “what capability is missing, and how do we make it both legible and enforceable for the agent?”
...
[[free recall miss]]: I didn't quite get this notion of working depth first, but I can see how it would fall out of their principle of [[no human -- coding]].
...
[[free recall miss]]: I caught the idea of making [[dim - legibility -- higher]], but "enforceability" kinda eluded me.  The only thing I can think of, as I read this again, is [[linting]], but I know there's more to it.  I'll keep my eyes peeled as I read further.
...
breaking down larger goals into smaller building blocks (design, code, review, test, etc), prompting the agent to construct those blocks
...
[[SDLC building block -- design]], [[SDLC building block -- code]], [[SDLC building block -- review]], [[SDLC building block -- test]]

To drive a PR to completion, we instruct Codex to review its own changes locally, request additional specific agent reviews both locally and in the cloud, respond to any human or agent given feedback, and iterate in a loop until all agent reviewers are satisfied (effectively this is a [[project - ralph wiggum]] loop). Codex uses our standard development tools directly (gh, local scripts, and [[repository-embedded skills]]) to gather context without humans copying and pasting into the CLI.
...
[[practice - specialized agent -- code review or eval]]
...
"both locally and in the cloud".  Hmm... what's the advantage here?

In practice, this meant working depth-first: breaking down larger goals into smaller building blocks (design, code, review, test, etc), prompting the agent to construct those blocks, and using them to unlock more complex tasks
...
It kind of sounds like they are saying that they sort of forced the agent to do the building blocks so if they ask for something directly, the agent isn't good enough to do those building blocks itself, but when directly driven towards doing them, it is

We also wired the Chrome DevTools Protocol into the agent runtime and created skills for working with DOM snapshots, screenshots, and navigation. This enabled Codex to reproduce bugs, validate fixes, and reason about UI behavior directly.
...
Hmm... I wonder what "wired the Chrome DevTools Protocol into the agent runtime" means?  Sounds more direct than an [[model context protocol - MCP]] or [[agent skill]].  They _did_ create skills, but those are separate: [[agent skill -- browser -- work with DOM snapshots]], [[agent skill -- browser -- work with screenshots]], [[agent skill -- browser -- navigation]]

Codex works on a fully isolated version of that app—including its logs and metrics, which get torn down once that task is complete. Agents can query logs with LogQL and metrics with PromQL. With this context available, prompts like “ensure service startup completes in under 800ms” or “no span in these four critical user journeys exceeds two seconds” become tractable.
...
The part I missed was that the agent has specific tools that allow it to interact with the logs and metrics better than just reading the logs and metrics
...
Their emphasis on logs and metrics me think about [[b the three pillars of AI observability - 2025-11]] and [[b AI will make formal verification go mainstream]].  It also makes me think about one of the specialized tools I wrote for meadow that is a essentially a [[Terminal Ui - TUI]] that ensures that everything gets cleanly committed as I use the app.  Like [[company - microsoft]]

### Documentation

*Note: in this section they describe their documentation.  I've been referring to this type of documentation as a [[documentation context graph]]*

Most of the way through there is an epic section about why a monolithic document is problematic and a graph is much better
...
[[long documents are problematic]]

There is a short map of context, essentially, that is directly injected into the agent.MD.
...
Makes me think about how skills are sometimes ignored and directly injecting information about them into the agent file is often more effective

In that section is a quote about when everything is important nothing is important.
It's also something about how [[documentation skews from code]] is inevitable in a large document because it's impossible to do things like cross check links look at metadata around how recently something was updated, etc.

We regularly see single Codex runs work on a single task for upwards of six hours (often while the humans are sleeping).
...
[[dim - task horizon length -- longer]]

Design documentation is catalogued and indexed, including verification status and a set of core beliefs that define agent-first operating principles. [[b ARCHITECTURE.md file]] provides a top-level map of domains and package layering. A quality document grades each product domain and architectural layer, tracking gaps over time.
...
The architecture.md file makes me think about [[the map is not the territory]] and how [[if you own the territory, perhaps you should make it easier to map]].

Plans are treated as first-class artifacts. Ephemeral lightweight plans are used for small changes, while complex work is captured in [[b OpenAI's Codex execution plans 2025-10]] with progress and decision logs that are checked into the repository. Active plans, completed plans, and known technical debt are all versioned and co-located, allowing agents to operate without relying on external context.
...
I wan't sure I had gotten this in my free recall, but it looks like I did.  [[coding agent operating without external context]] makes it seem like they _don't_ rely on something like [[github issues]] or [[project - Beads]], but they do, also... just at a higher level.

We enforce this mechanically. Dedicated linters and CI jobs validate that the knowledge base is up to date, cross-linked, and structured correctly. A recurring “doc-gardening” agent scans for stale or obsolete documentation that does not reflect the real code behavior and opens fix-up pull requests.
...
Basically [[validation script]]s... some of them are [[custom linting rule]]s.  [[specialized agent -- doc-gardening]]

### Agent Legibility

Giving Codex more context means organizing and exposing the right information so the agent can reason over it, rather than overwhelming it with ad-hoc instructions. In the same way you would onboard a new teammate on product principles, engineering norms, and team culture (emoji preferences included), giving the agent this information leads to better-aligned output.
...
[[The onboarding a new teammate lens to agent context engineering]]
...
kind of the opposite of [[company - Glean]], where it helps you work with all those other sources.  In this case, the sources are pulled into the repo (and organized).

This framing clarified many tradeoffs. We favored dependencies and abstractions that could be fully internalized and reasoned about in-repo. Technologies often described as “boring” tend to be easier for agents to model due to composability, api stability, and representation in the training set. In some cases, it was cheaper to have the agent reimplement subsets of functionality than to work around opaque upstream behavior from public libraries. For example, rather than pulling in a generic `p-limit`-style package, we implemented our own map-with-concurrency helper: it’s tightly integrated with our OpenTelemetry instrumentation, has 100% test coverage, and behaves exactly the way our runtime expects.
...
[[Coding agents means that it makes less sense to use external libraries]]

### Enforcing architecture and taste

Documentation alone doesn’t keep a fully agent-generated codebase coherent. **By enforcing invariants, not micromanaging implementations, we let agents ship fast without undermining the foundation.** For example, we require Codex to [[b parse, don't validate|parse data shapes at the boundary⁠]], but are not prescriptive on how that happens (the model seems to like [[project - Zod]], but we didn’t specify that specific library).
...
[[invariant testing]]
...
[[b parse, don't validate]]

todo: I don't think I got through this section fully

## Throughput changes the merge philosophy

todo: read this section and fill this out

Hmm... merge philosophy
...
Perhaps they touch on this: [[specialized agent -- code merge]]
