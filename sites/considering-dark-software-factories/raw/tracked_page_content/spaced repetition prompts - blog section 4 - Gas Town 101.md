^ [[spaced repetition prompts]] - blog section 4 - Gas Town 101

---

## [[Blog Post -- Section 4 - Gas Town 101]]


What are the two types of coding workers in Gas Town?
?
[[Term -- Polecats|Polecats]] (ephemeral) and [[Term -- The Crew|The Crew]] (long-lived).
<!--SR:!2026-03-08,1,230-->

<!--MEADOW_SR_GUID:cbd003324f2e9-->
<!--GUID:6a0a31cf42832-->



What does [[Term -- The Town|The Town]] orchestrate?
?
All agents — workers, patrols, and management — across all [[Term -- Rigs|Rigs]].
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:013d5e9444b07-->
<!--GUID:6497c0db5a5af-->



Where does [[Term -- The Town|The Town]] live on disk?
?
A directory like `~/gt`, with project [[Term -- Rigs|Rigs]] underneath it.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:3fd559ed2b9b6-->
<!--GUID:5cb368f15bd8b-->



What is [[Term -- The Town|The Town]] implemented as?
?
A Go binary called `gt`, kept in its own repo.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:9432ec53920af-->
<!--GUID:94727e5667ccc-->



How does a [[Term -- Rigs|Rig]] relate to a git repo?
?
Each [[Term -- Rigs|Rig]] is a git repo placed under [[Term -- The Town|Town]] management.
<!--SR:!2026-03-21,8,250-->

<!--MEADOW_SR_GUID:0aafe1e447d52-->
<!--GUID:ad59031cc4345-->



Which roles are per-[[Term -- Rigs|rig]]?
?
[[Term -- The Witness|Witness]], [[Term -- Polecats|Polecats]], [[Term -- Refinery|Refinery]], and [[Term -- The Crew|Crew]].
<!--SR:!2026-03-15,2,230-->

<!--MEADOW_SR_GUID:8b764249e025b-->
<!--GUID:32d666ccfe7fe-->



Which roles are town-level?
?
[[Term -- The Mayor|Mayor]], [[Term -- The Deacon|Deacon]], and [[Term -- Dogs|Dogs]].
<!--SR:!2026-03-08,1,230-->

<!--MEADOW_SR_GUID:6e86667574327-->
<!--GUID:d6bc544cf8424-->



What distinguishes [[Term -- The Overseer|The Overseer]] from all other Gas Town roles?
?
The Overseer is the only human — everyone else is an agent.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:1fc3e577b7037-->
<!--GUID:78b7a7603783e-->



How does [[Term -- The Overseer|The Overseer]] communicate with agents?
?
Through [[Term -- Town Mail|Town Mail]], via their own [[Term -- Inbox|Inbox]].
<!--SR:!2026-03-14,2,230-->

<!--MEADOW_SR_GUID:bad596f0df233-->
<!--GUID:6be51ec0152f0-->



Why do you talk to [[Term -- The Mayor|The Mayor]] more than other agents?
?
It's your concierge and chief-of-staff — it kicks off work [[Term -- Convoy|Convoy]]s and reports back when they finish.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:1e35cca359894-->
<!--GUID:060bdf474e2cc-->



What do [[Term -- Polecats|Polecats]] produce?
?
[[code merge request|Merge Requests (MRs)]].
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:fcd4ffc198dd1-->
<!--GUID:6dd7688dcd7ee-->



How do [[Term -- Polecats|Polecats]] lifecycles differ from [[Term -- The Crew|The Crew]] lifecycles?
?
[[Term -- Polecats|Polecats]] are ephemeral and decommissioned after their MR merges. [[Term -- The Crew|Crew]] members are long-lived with persistent identities.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:86594c6ce5e3c-->
<!--GUID:67a6bcaa76f92-->



What happens to [[Term -- Polecats|Polecats]] after their MR is merged?
?
They are fully decommissioned, though their names are recycled.
<!--SR:!2026-03-21,8,250-->

<!--MEADOW_SR_GUID:cf7cf482ae14b-->
<!--GUID:b0752c4e502e2-->


What about a [[Term -- Polecats|Polecats]] remains, even after they are decommissioned?
?
Their name remains, and is recycled
<!--GUID:3ec521924af77-->

<!--MEADOW_SR_GUID:9d5393d5485f4-->



Who do [[Term -- The Witness|Witnesses]] watch over?
?
The [[Term -- Polecats|Polecats]].
<!--SR:!2026-03-11,4,270-->

<!--MEADOW_SR_GUID:65cfd2b1e6017-->
<!--GUID:579d861f9ce83-->



Why do you need a [[Term -- The Witness|Witness]]?
?
When enough [[Term -- Polecats|Polecats]] are swarming, some get stuck and need to be hustled along.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:f450b4cbbb597-->
<!--GUID:6628d6c8431f1-->



What problem does the [[Term -- Refinery|Refinery]] solve?
?
The [[code merge queue|Merge Queue]] problem — workers conflicting over rebasing/merging when swarming.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:86781639a17a0-->
<!--GUID:4209e5ad16d08-->



Why is merging hard when [[Term -- Polecats|Polecats]] swarm?
?
The baseline changes so much that late mergers face an unrecognizable new head and may need to completely reimplement.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:9e1851077d699-->
<!--GUID:bbe0574cc2a3b-->



How does the [[Term -- Refinery|Refinery]] merge changes?
?
One at a time
<!--SR:!2026-03-11,4,270-->

<!--MEADOW_SR_GUID:7930fa4a35785-->
<!--GUID:efbe4b2cdeda7-->



What kind of loop does [[Term -- The Deacon|The Deacon]] run?
?
A [[Term -- Patrol|patrol]] — a well-defined workflow it repeats continuously.
<!--SR:!2026-03-22,9,250-->

<!--MEADOW_SR_GUID:a2baaa69497a1-->
<!--GUID:9cf0a40c60378-->



How does [[Term -- The Deacon|The Deacon]] keep Gas Town running?
?
It receives a "Do Your Job" (DYFJ) signal every couple minutes and propagates it downward to other workers.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:9166ce2b24f4f-->
<!--GUID:2da12ab2971f6-->



How do [[Term -- Dogs|Dogs]] relate to [[Term -- The Deacon|The Deacon]]?
?
They're [[Term -- The Deacon|The Deacon]]'s personal crew, handling maintenance and handyman tasks so the Deacon stays focused on its patrol.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:e26a3b64cc733-->
<!--GUID:d47c04d643cb1-->



Why were [[Term -- Dogs|Dogs]] added?
?
The [[Term -- The Deacon|Deacon]]'s patrol got overloaded with responsibilities and needed helpers to stay focused.
<!--SR:!2026-03-08,1,230-->

<!--MEADOW_SR_GUID:d168988e158a0-->
<!--GUID:377b9236fe863-->



What does [[Term -- Boot the Dog|Boot the Dog]] decide every 5 minutes?
?
Whether [[Term -- The Deacon|The Deacon]] needs a heartbeat, a nudge, a restart, or to be left alone.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:0c5472cbefb90-->
<!--GUID:3a0a84594bbf2-->



Why does [[Term -- Boot the Dog|Boot the Dog]] exist instead of the daemon pinging [[Term -- The Deacon|The Deacon]] directly?
?
The daemon kept interrupting [[Term -- The Deacon|The Deacon]] with heartbeats and pep talks — [[Term -- Boot the Dog|Boot]] absorbs that so the Deacon can focus.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:87eb4228f9ed1-->
<!--GUID:3da233f5144d1-->



How do [[Term -- The Crew|The Crew]] differ from [[Term -- Polecats|Polecats]] in terms of management?
?
[[Term -- The Crew|Crew]] work directly for [[Term -- The Overseer|the Overseer]], not managed by [[Term -- The Witness|The Witness]]. [[Term -- Polecats|Polecats]] are managed by the Witness.
<!--SR:!2026-03-08,1,230-->

<!--MEADOW_SR_GUID:60e7a88298228-->
<!--GUID:a053ba86ac352-->



What kind of work are [[Term -- The Crew|The Crew]] best suited for?
?
Design work with lots of back-and-forth.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:9fbf716413b86-->
<!--GUID:730fb7f63fc5c-->



What does "graceful degradation" mean in Gas Town?
?
Every worker can operate independently. You can run whichever parts you want, even in "no-tmux" mode with plain Claude Code sessions.
<!--SR:!2026-03-10,3,250-->

<!--MEADOW_SR_GUID:84bef1ea760b8-->
<!--GUID:1331a98d01727-->



Which characters do [[Term -- Patrol|Patrol]]s?
?
[[Term -- The Deacon|The Deacon]] and [[Term -- The Witness|The Witness]]
<!--GUID:b65b729a40a92-->

<!--MEADOW_SR_GUID:4ca9c1c7a721e-->



In Gas Town, which is more enduring... an [[Term -- Agent|agent]] or a [[Term -- Session|session]]?
?
The agent.  An agent is the persistent identity (the "pet"); a session is the ephemeral Claude Code process thrown at work (the "cattle"). Sessions come and go, but the agent endures.
<!--GUID:658c64ed383ac-->

<!--MEADOW_SR_GUID:b33805c54dd5b-->



If a Claude Code session crashes mid-task, what survives — the agent or the session?
?
The [[Term -- Agent|agent]]. Its identity, state, and work live in [[project - Beads|Beads]]. The [[Term -- Session|session]] is disposable cattle — just spin up another one.
<!--GUID:410614d829164-->

<!--MEADOW_SR_GUID:f2c3635ef8558-->



How does an [[Term -- Agent|agent]] endure an environment crash?
?
The [[Term -- Agent|agent]]'s identity, state, and work live in [[project - Beads|Beads]], which is git-backed.
<!--GUID:c43c1bb40d008-->

<!--MEADOW_SR_GUID:1e49423d6de8f-->

---

**Next section:** [[spaced repetition prompts - blog section 6 - Gastown Universal Propulsion Principle|section 6 - Gastown Universal Propulsion Principle]]

---

#flashcards/gas-town/section-4--gas-town-101