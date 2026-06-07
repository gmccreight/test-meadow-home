^ fix the [[agent harness]] so that it fixes the [[code]]

---

**fix the harness so that it fixes the code** means treating bad <span class="link-not-tracked">link not tracked</span> as evidence of a missing capability in the [[agent harness]], not as a one-off patch target.

When a [[agentic coding|coding agent]] forgets a unit test, drifts architecturally, or misses a verification step, the durable fix is usually a [[mechanisms for making agents more reliable|mechanism]]: a better prompt, [[agent skill]], [[custom linting rule]], [[validation script]], reviewer agent, CI check, or observability hook. The point is to convert the failure into a repeatable constraint or [[feedback loop]] so future generated code improves automatically.

This is a core implication of [[no human -- coding]] and [[harness engineering]]: human engineers move upstream from editing output to designing the environment that produces acceptable output.

Related: <span class="link-not-tracked">link not tracked</span>, <span class="link-not-tracked">link not tracked</span>, [[practice - custom linting rules that inject in-repo documentation as context]]
