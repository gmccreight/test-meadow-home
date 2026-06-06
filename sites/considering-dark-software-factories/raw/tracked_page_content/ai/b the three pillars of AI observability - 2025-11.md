https://www.braintrust.dev/blog/three-pillars-ai-observability

[[company - braintrust]] [[person - Ankur Goyal]]

[[AI observability]]

Probably [[traces, evals, and annotations - TEA]]

Classical app stacks are deterministic. You instrument code paths, emit metrics, capture logs, and (if needed) follow a trace to a root cause. AI systems are probabilistic and data‑coupled. The same input can produce different outputs. Quality depends on prompts, models, retrieval, tools, context length, and training data. Observability must therefore explain behavior and tie it to measurable outcomes, not just runtime health
...
[[deterministic]]
...
[[AI observability must explain behavior and tie to measurable outcomes]]


[[trace]]s: Reconstruct the full [[decision path]] for a request, across [[model call]]s, [[tool use|tools]], [[retrieval]], and [[control flow]]

[[evals]]: Quantify performance, both in production (online) and in dev and CI (offline), to understand how well your application works and systematically improve it
...
[[dim - model performance]] (but not really _model_ performance... more like [[compound system]] performance)

[[annotation]]: Create corrective signals for both your application and evaluators, to inject taste and ground results in user expectations.
...
[[annotations create corrective signals for your application and evaluators]]
...
Hmm... what is an [[evaluator]]?

### Pillars

#### Pillar 1 - Traces

[[traces should provide reproducible context, not just spans]]

Traditionally, tracing helps you to understand performance bottlenecks: what functions or APIs are called, how long do they take, and how do they interleave. While this remains relevant in AI, the primary use case for tracing in AI is understanding what happened in the first place. Which tools were called, and why? What context did the LLM have while generating a strange output?

Users also don't want to jump between three disjointed experiences [[metrics, logs, and traces]] to create a full picture of user behavior, so in AI, these have collapsed into one thing: tracing
...
 [[AI observability]] [[metrics, logs, and traces]] collapse into [[trace]]s

#### Pillar 2 - Evals

[[systematic]]ally improve your product

You can't stare at a prompt and know what's going to happen. AI systems are inherently non-deterministic, and therefore you must measure their behavior to know how they perform. This process is called "evaluation", and you can do it both in production ("online") and in dev and CI ("offline").
...
The process is called [[evaluation]].  [[online monitoring]]  [[diff - pre-deploy evals vs. online monitoring]]

The core primitive of evaluation is [[scoring]]. Scoring allows you to look at an entire agent interaction ([[trace]]) or turn ([[span]]) and quantify it. Usually, this means producing a number (for example, how factually grounded is the answer?), but it can also be categorical (for example, what type of error is this?). The best teams use online evals to help them discover what to test in dev and CI.
...
[[using online evals to help discover what to test in dev and CI]]

For example, if you discover that your agent is highly repetitive, you can write an evaluator to detect that case, and then capture a handful of real-world examples that you can test on your laptop. While testing, you should use _exactly the same_ tracing that you run in production, and assess how the changes you make affect both the repetition score and other performance indicators that you track. Once you feel confident, you can ship a new iteration, and see how it affects production eval scores.
...
[[example score -- repetition]]
...
This _seems_ to fly in the face of [[person - Hamel Husain]]'s suggestion [[prefer binary pass or fail evaluations instead of scaled ones]] unless they are actually suggesting a binary score

#### Pillar 3 - Annotation

In traditional observability, when you notice something is wrong, the next action to take is almost always to update code and try again. However, in AI, incorrect behavior often requires input from an expert (product manager, subject-matter expert, or even a user) who can clarify the behavior. The best workflows for annotation involve curating interesting examples that would benefit from annotation, flagging them for review, and then utilizing the annotated data in evals to improve performance.
...
[[annotation]] [[evals persona -- domain expert]] [[curating interesting examples]]
...
[[utilizing annotations in evals]] to improve [[dim - model performance]]

Once again, this breaks core assumptions in traditional observability. First, traces must be mutable, so that you can save annotations and query them alongside other metadata. Supporting updates on traces at "agent-scale" makes the agent-tracing database problem even more challenging. Second, the users who annotate are rarely developers, and so they benefit from UIs that simplify the data they must annotate into its simplest components.
...
[[the users who annotate are rarely developers]] ... maybe they are [[evals persona -- domain expert]]s... that simplification of the tooling is one reason why [[person - Hamel Husain]] suggests [[building your own human eval tools]].  Because you can build for the other personas.  [[UI-UX]].  Also captured in the ideas that it [[can be helpful to represent data in a more user-friendly review format]]

Once you capture annotations, you should save them into [[eval dataset|dataset]]s which are the basis for [[offline eval]]s. Each time you want to make a change to your application, you should evaluate it against the datasets you've accumulated to approximate its impact. Although people often use the term [[golden-set|golden dataset]], we have seen a shift away from this concept in favor of a more fluid approach called "dataset reconciliation", where the goal shifts to incrementally and frequently updating datasets to represent real-world behaviors, rather than commissioning one up front.
...
[[saving annotations into your eval dataset]]
...
A move away from [[golden-set]] to [[dataset reconciliation]].  [[diff - golden set vs. dataset reconciliation]]

### Other stuff

We've built annotation tools directly into the trace viewer so product managers, domain experts, and other stakeholders can review traces, flag issues, correct outputs, and build datasets without getting lost in JSON or touching code. These annotations flow directly into your evaluation [[eval dataset]]s, creating a continuous improvement loop that leverages expertise across your entire team.
...
[[evals persona -- product manager]] 

If you're building AI that real customers rely on, you need to:
1. **Trace everything**. [[you can't improve what you can't measure]], and you can't measure what you can't see.
2. **Run evals constantly**. Both online (to catch regressions) and offline (to test improvements) x [[evals should be easy and cheap to run]]
3. **Build annotation into your workflow**. The best AI systems improve over time by learning from expert feedback.