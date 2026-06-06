https://x.com/gsd_foundation/status/2030361888681239003?s=20

The rule: If you could write an if-else that handles it correctly every time, it must be deterministic code — not LLM reasoning. Every token the model spends on mechanical operations is a token wasted and a failure mode introduced.
...
[[determinism where possible]]

Avoid [[context rot]]

[[agent task scope should be narrow]]

Before a task starts, the system pre-assembles everything the agent needs:
- The task plan (goal, steps, must-haves)
- Compressed summaries from dependency slices
- Milestone-level context and decisions
- Continue-here data if resuming interrupted work
This is injected automatically. The agent never has to `grep` for project structure, `read` state files to figure out where it is, or search for what was built in prior slices. If it does, the [[context assembly]] is broken — that's a bug, not a workflow.
:
The goal is zero discovery calls. Every token the agent spends on "where am I, what exists, what was decided" is a token not spent on actual implementation.
......
This would let the agent stay in the [[context window zone -- the smart zone]] more easily.  But also this feels exactly like [[Claude Code's planning, then context clearing, then implementing]].  What's the difference?  [[determinism where possible]]... _maybe_?

One critical rule: never summarize summaries. Each summary level regenerates from the level below plus actual code state. A slice summary comes from task summaries, not from a compressed version of a prior slice summary. This prevents the compounding information loss you get when you keep compressing compressed text


The output is a `context.md` file — a structured record of every decision with your reasoning. This file gets injected into all downstream work: planning, execution, verification, everything. When the agent is implementing task 4 of slice 2, it still has your discuss-phase decisions in context. It doesn't re-debate them. It doesn't silently make a different choice because it forgot what you said. The decisions are locked and flow through the entire pipeline.
...
This feels like one or more [[documentation context graph -- document]].  Cool thing is it auto-injects for hierarchically descendent work when you do [[decomposing work into narrowly scoped work]]

Here's a question that should bother anyone using AI coding agents: when the agent says "done," how do you actually know?
:
You can read the code. You can check that files exist. But for most people, the real question is: does it actually work the way I asked? Can I go use it and see the thing I was promised?
:
GSD generates this automatically. Every time a slice completes, the system produces a User Acceptance Test script — a human-readable document that tells you exactly how to verify what was built. Not as an afterthought. Not as something you have to ask for. It's baked into the completion flow. Finish a slice, get a test script.
...
[[User Acceptance Test - UAT]]

Reply says [[agent swarm]]s were a hard problem but solved now