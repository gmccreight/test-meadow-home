^ [[agent skill wrapped]] [[script]]s

---

For scripts where there is a moderate possibility of failure, and the remediation would be to re-run it with an agent to fix it, it is better to simply wrap the script in an agent skill so the agent can immediately help fix the problems if they happen.

This adds a little bit of latency, but then it's more fire and forget.  In practice I get less annoyed.

Related to [[for simple workflows, smart agents can effectively run them as deterministic workflows]]