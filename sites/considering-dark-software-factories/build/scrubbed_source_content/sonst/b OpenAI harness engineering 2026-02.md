https://openai.com/index/harness-engineering/

^ [[company - OpenAI]] [[agent harness]] [[harness engineering]]

---

Notes:

* this blog post
* [[free recall - Open AI harness blog post - 2026-02]] (one day later)
* <span class="link-not-tracked">link not tracked</span> (three days after that)
* <span class="link-not-tracked">link not tracked</span> (throughout)

---

[[company - OpenAI]]

Throughout the development process, humans never directly contributed any code. This became a core philosophy for the team: **no manually-written code**.
...
[[no human -- coding]]

Because the only way to make progress was to get Codex to do the work, human engineers always stepped into the task and asked: “what capability is missing, and how do we make it both legible and enforceable for the agent?” X [[fix the harness so that it fixes the code]]

Codex uses our standard development tools directly (gh, local scripts, and repository-embedded skills) to gather context without humans copying and pasting into the CLI. ^codex-uses-our-standard-dev-tools

Humans may review pull requests, but aren’t required to. Over time, we’ve pushed almost all review effort towards being handled agent-to-agent.
...
[[no human -- code review]]

As code throughput increased, our bottleneck became human QA capacity. Because the fixed constraint has been human time and attention, we’ve worked to add more capabilities to the agent by making things like the application UI, logs, and app metrics themselves directly legible to Codex.
...
[[dim - legibility -- higher]]
...
[[bottleneck - human reviewers]] in [[QA]]

For example, we made the app bootable per [[git worktree]], so Codex could launch and drive one instance per change

We did the same for observability tooling. Logs, metrics, and traces are exposed to Codex via a local observability stack that’s ephemeral for any given worktree. Codex works on a fully isolated version of that app—including its logs and metrics, which get torn down once that task is complete. Agents can query logs with LogQL and metrics with PromQL. With this context available, prompts like “ensure service startup completes in under 800ms” or “no span in these four critical user journeys exceeds two seconds” become tractable.
...
[[observability stack]] was directly built-in to [[project - Codex|Codex]] ^observability-stack-built-in-to-codex

With this context available, prompts like “ensure service startup completes in under 800ms” or “no span in these four critical user journeys exceeds two seconds” become tractable.

We enforce this mechanically. Dedicated linters and CI jobs validate that the knowledge base is up to date, cross-linked, and structured correctly. A recurring “doc-gardening” agent scans for stale or obsolete documentation that does not reflect the real code behavior and opens fix-up pull requests
...
[[maintenance agent]]s

Because the repository is entirely agent-generated, it’s optimized first for _Codex’s__legibility_. In the same way teams aim to improve navigability of their code for new engineering hires, our human engineers’ goal was making it possible for an agent to reason about the full business domain **directly from the repository itself.**
...
[[dim - legibility -- higher]]

Giving Codex more context means organizing and exposing the right information so the agent can reason over it, rather than overwhelming it with ad-hoc instructions. In the same way you would onboard a new teammate on product principles, engineering norms, and team culture (emoji preferences included), giving the agent this information leads to better-aligned output.
...
[[progressive disclosure is similar to a skill tree]]

In some cases, it was cheaper to have the agent reimplement subsets of functionality than to work around opaque upstream behavior from public libraries. For example, rather than pulling in a generic `p-limit`-style package, we implemented our own map-with-concurrency helper: it’s tightly integrated with our OpenTelemetry instrumentation, has 100% test coverage, and behaves exactly the way our runtime expects

The diagram below shows the rule: within each business domain (e.g. App Settings), code can only depend “forward” through a fixed set of layers (Types → Config → Repo → Service → Runtime → UI). Cross-cutting concerns (auth, connectors, telemetry, feature flags) enter through a single explicit interface: Providers. Anything else is disallowed and enforced mechanically.

This is the kind of architecture you usually postpone until you have hundreds of engineers. With coding agents, it’s an early prerequisite: the constraints are what allows speed without decay or architectural drift.
...
[[agentic coding only works well with human architectural direction and taste]]

Because the lints are custom, we write the error messages to inject remediation instructions into agent context.

In a human-first workflow, these rules might feel pedantic or constraining. With agents, they become multipliers: once encoded, they apply everywhere at once.
