^ [[spaced repetition prompts]] - blog section 6 - Gastown Universal Propulsion Principle

## [[Blog Post -- Section 6 - Gastown Universal Propulsion Principle]]


In Gas Town, which is more enduring... an [[Term -- Agent|agent]] or a [[Term -- Session|session]]?
?
The agent.  An agent is the persistent identity (the "pet"); a session is the ephemeral Claude Code process thrown at work (the "cattle"). Sessions come and go, but the agent endures.
...
[[pets vs cattle]]
<!--GUID:fc30644380e50-->

<!--MEADOW_SR_GUID:7b08e374b540b-->



If a Claude Code session crashes mid-task, what survives — the agent or the session?
?
The [[Term -- Agent|agent]]. Its identity, state, and work live in [[project - Beads|Beads]]. The [[Term -- Session|session]] is disposable cattle — just spin up another one.
<!--GUID:419dac59828d0-->

<!--MEADOW_SR_GUID:756c3cd33fc6d-->



How does an [[Term -- Agent|agent]] endure an environment crash?
?
The [[Term -- Agent|agent]]'s identity, state, and work live in [[project - Beads|Beads]], which is git-backed.
<!--GUID:7d3100f8c56e9-->

<!--MEADOW_SR_GUID:76593f38264c2-->



Which [[Term -- Bead|Bead]] type is used for [[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]]?
?
[[Term -- Hook|Hook]]
<!--GUID:a1b2c3d4e5f60-->

<!--MEADOW_SR_GUID:ab05b3ea76c83-->



What does a [[Term -- Role Bead|Role Bead]] represent?
?
A worker's [[Term -- Identity Type|identity type]] — like a domain table describing the role, with priming information.
<!--GUID:b2c3d4e5f6a71-->

<!--MEADOW_SR_GUID:db074223c36f5-->



What makes a [[Term -- Pinned Bead|Pinned Bead]] different from a regular [[Term -- Bead|Bead]]?
?
Pinned Beads float like yellow-sticky notes — they never get closed and don't show up in `bd ready`.
<!--GUID:c3d4e5f6a7b82-->

<!--MEADOW_SR_GUID:324b3ed91579a-->



Where do you hang [[Term -- Molecule|Molecules]] for a [[Term -- Worker|worker]] to execute?
?
On the worker's [[Term -- Hook|Hook]] — a special [[Term -- Pinned Bead|Pinned Bead]] unique to that agent.
<!--GUID:d4e5f6a7b8c93-->

<!--MEADOW_SR_GUID:076a3370d27b8-->



How does work get placed on a [[Term -- Worker|worker]]'s [[Term -- Hook|Hook]]?
?
With `gt sling` — you sling work to workers and it goes on their hook. You can start immediately, defer, or make them restart first.
<!--SR:!2026-04-14,4,270-->

<!--MEADOW_SR_GUID:1e2ebfb57282e-->
<!--GUID:e5f6a7b8c9d04-->

<!--MEADOW_SR_GUID:6a510cb4a6ca3-->



What happens when a [[Term -- Worker|worker]] does a [[Term -- handoff|handoff]]?
?
The worker gracefully cleans up and restarts its session. If it's hooked, [[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]] keeps it working automatically.
<!--GUID:f6a7b8c9d0e15-->

<!--MEADOW_SR_GUID:e6eb5e7bd05de-->



Why doesn't [[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]] always work in practice?
?
Claude Code is too polite — it sometimes ignores the hook and sits waiting for user input instead of running automatically.
...
[[agent problem - Claude Code is polite and waits for user input]]
<!--GUID:a7b8c9d0e1f26-->

<!--MEADOW_SR_GUID:06022445173b0-->

---

**Next section:** [[spaced repetition prompts - blog section 7 - The GUPP Nudge|section 7 - The GUPP Nudge]]

---

<span class="link-not-tracked">link not tracked</span>
