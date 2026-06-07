https://www.braintrust.dev/blog/three-pillars-ai-observability

<span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>

Probably <span class="link-not-tracked">link not tracked</span>

Classical app stacks are deterministic. You instrument code paths, emit metrics, capture logs, and (if needed) follow a trace to a root cause. AI systems are probabilistic and data‑coupled. The same input can produce different outputs. Quality depends on prompts, models, retrieval, tools, context length, and training data. Observability must therefore explain behavior and tie it to measurable outcomes, not just runtime health
...
<span class="link-not-tracked">link not tracked</span>
...
<span class="link-not-tracked">link not tracked</span>


[[trace]]s: Reconstruct the full <span class="link-not-tracked">link not tracked</span> for a request, across <span class="link-not-tracked">link not tracked</span>s, <span class="link-not-tracked">link not tracked</span>, <span class="link-not-tracked">link not tracked</span>, and <span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>: Quantify performance, both in production (online) and in dev and CI (offline), to understand how well your application works and systematically improve it
...
<span class="link-not-tracked">link not tracked</span> (but not really _model_ performance... more like [[compound system]] performance)

<span class="link-not-tracked">link not tracked</span>: Create corrective signals for both your application and evaluators, to inject taste and ground results in user expectations.
...
<span class="link-not-tracked">link not tracked</span>
...
Hmm... what is an <span class="link-not-tracked">link not tracked</span>?

### Pillars

#### Pillar 1 - Traces

<span class="link-not-tracked">link not tracked</span>

Traditionally, tracing helps you to understand performance bottlenecks: what functions or APIs are called, how long do they take, and how do they interleave. While this remains relevant in AI, the primary use case for tracing in AI is understanding what happened in the first place. Which tools were called, and why? What context did the LLM have while generating a strange output?

Users also don't want to jump between three disjointed experiences <span class="link-not-tracked">link not tracked</span> to create a full picture of user behavior, so in AI, these have collapsed into one thing: tracing
...
 <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span> collapse into [[trace]]s

#### Pillar 2 - Evals

<span class="link-not-tracked">link not tracked</span>ally improve your product

You can't stare at a prompt and know what's going to happen. AI systems are inherently non-deterministic, and therefore you must measure their behavior to know how they perform. This process is called "evaluation", and you can do it both in production ("online") and in dev and CI ("offline").
...
The process is called <span class="link-not-tracked">link not tracked</span>.  <span class="link-not-tracked">link not tracked</span>  <span class="link-not-tracked">link not tracked</span>

The core primitive of evaluation is <span class="link-not-tracked">link not tracked</span>. Scoring allows you to look at an entire agent interaction ([[trace]]) or turn (<span class="link-not-tracked">link not tracked</span>) and quantify it. Usually, this means producing a number (for example, how factually grounded is the answer?), but it can also be categorical (for example, what type of error is this?). The best teams use online evals to help them discover what to test in dev and CI.
...
<span class="link-not-tracked">link not tracked</span>

For example, if you discover that your agent is highly repetitive, you can write an evaluator to detect that case, and then capture a handful of real-world examples that you can test on your laptop. While testing, you should use _exactly the same_ tracing that you run in production, and assess how the changes you make affect both the repetition score and other performance indicators that you track. Once you feel confident, you can ship a new iteration, and see how it affects production eval scores.
...
<span class="link-not-tracked">link not tracked</span>
...
This _seems_ to fly in the face of [[person - Hamel Husain]]'s suggestion <span class="link-not-tracked">link not tracked</span> unless they are actually suggesting a binary score

#### Pillar 3 - Annotation

In traditional observability, when you notice something is wrong, the next action to take is almost always to update code and try again. However, in AI, incorrect behavior often requires input from an expert (product manager, subject-matter expert, or even a user) who can clarify the behavior. The best workflows for annotation involve curating interesting examples that would benefit from annotation, flagging them for review, and then utilizing the annotated data in evals to improve performance.
...
<span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span>
...
<span class="link-not-tracked">link not tracked</span> to improve <span class="link-not-tracked">link not tracked</span>

Once again, this breaks core assumptions in traditional observability. First, traces must be mutable, so that you can save annotations and query them alongside other metadata. Supporting updates on traces at "agent-scale" makes the agent-tracing database problem even more challenging. Second, the users who annotate are rarely developers, and so they benefit from UIs that simplify the data they must annotate into its simplest components.
...
<span class="link-not-tracked">link not tracked</span> ... maybe they are <span class="link-not-tracked">link not tracked</span>s... that simplification of the tooling is one reason why [[person - Hamel Husain]] suggests <span class="link-not-tracked">link not tracked</span>.  Because you can build for the other personas.  <span class="link-not-tracked">link not tracked</span>.  Also captured in the ideas that it <span class="link-not-tracked">link not tracked</span>

Once you capture annotations, you should save them into <span class="link-not-tracked">link not tracked</span>s which are the basis for <span class="link-not-tracked">link not tracked</span>s. Each time you want to make a change to your application, you should evaluate it against the datasets you've accumulated to approximate its impact. Although people often use the term <span class="link-not-tracked">link not tracked</span>, we have seen a shift away from this concept in favor of a more fluid approach called "dataset reconciliation", where the goal shifts to incrementally and frequently updating datasets to represent real-world behaviors, rather than commissioning one up front.
...
<span class="link-not-tracked">link not tracked</span>
...
A move away from <span class="link-not-tracked">link not tracked</span> to <span class="link-not-tracked">link not tracked</span>.  <span class="link-not-tracked">link not tracked</span>

### Other stuff

We've built annotation tools directly into the trace viewer so product managers, domain experts, and other stakeholders can review traces, flag issues, correct outputs, and build datasets without getting lost in JSON or touching code. These annotations flow directly into your evaluation <span class="link-not-tracked">link not tracked</span>s, creating a continuous improvement loop that leverages expertise across your entire team.
...
<span class="link-not-tracked">link not tracked</span> 

If you're building AI that real customers rely on, you need to:
1. **Trace everything**. <span class="link-not-tracked">link not tracked</span>, and you can't measure what you can't see.
2. **Run evals constantly**. Both online (to catch regressions) and offline (to test improvements) x <span class="link-not-tracked">link not tracked</span>
3. **Build annotation into your workflow**. The best AI systems improve over time by learning from expert feedback.