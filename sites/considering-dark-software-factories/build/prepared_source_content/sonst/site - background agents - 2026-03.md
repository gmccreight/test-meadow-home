[https://background-agents.com](https://background-agents.com/)

*Site structure note: structured a bit like [[site - AI 2027]] and also a bit like [[Bartosz-style explorable explanation]].    A site, so it changes, but I read it in 2026-03.

---

[[background agent]] seems like [[cloud agent]]s

The agent runs on a server or locally. When it needs to execute code, it calls a separate remote sandbox via API. The sandbox runs the code and returns the result. This keeps secrets and execution somewhat isolated, but the agent can only execute code and not fully develop.
...
[[sandbox as a tool]]


[[scheduled agent]]s are triggered on a timer. Predictable, bounded, high-volume — dependency updates, lint sweeps, coverage enforcement.
...
See also [[practice - background check]]s

[[event-driven agent]] : triggered by system events — a PR opened, a CVE published, an alert fired. Reactive, concurrent, always listening.

Updating one repository is a coding agent task. Updating 500 is a fleet task. The same sandbox, replicated across every repository that needs the change — parallel provisioning, progress tracking, aggregated results. This is where individual productivity becomes organizational throughput.
...
[[agent fleet]]
...
[[diff - agent fleet vs. agent swarm]]

