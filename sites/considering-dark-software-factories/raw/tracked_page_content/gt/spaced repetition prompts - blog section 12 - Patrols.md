^ [[spaced repetition prompts]] - blog section 12 - Patrols

---

## [[Blog Post -- Section 12 - Patrols]]


What is a [[Term -- Patrol|Patrol]] implemented as?
?
An ephemeral ([[Term -- Wisp|Wisp]]) workflow that the agent runs in a loop.
<!--GUID:a1f3c7d829e41-->

<!--MEADOW_SR_GUID:97e2e5f9b04aa-->


What happens when a [[Term -- Patrol|Patrol]] worker finds no work in its steps?
?
Exponential backoff — the agent waits longer and longer before starting the next patrol.
<!--GUID:b2e4d8f93a052-->

<!--MEADOW_SR_GUID:1393066bd33b4-->


What wakes a sleeping [[Term -- Patrol|Patrol]] worker?
?
Any mutating `gt` or `bd` command will wake the town.
<!--GUID:c3f5e9a04b163-->

<!--MEADOW_SR_GUID:c3711b74610ee-->


What does the [[Term -- Refinery|Refinery]]'s patrol do at its core?
?
Processes the [[code merge queue|Merge Queue]] until it's empty or it needs to recycle the session.
<!--GUID:d4a6fab15c274-->

<!--MEADOW_SR_GUID:253c56a6a16c4-->


Who does [[Term -- The Witness|The Witness]] check in on?
?
The [[Term -- Polecats|Polecats]] and [[Term -- Refinery|Refinery]]s — but it also peeks in on [[Term -- The Deacon|The Deacon]].
<!--GUID:e5b7abc26d385-->

<!--MEADOW_SR_GUID:c46838f1f8b03-->


What level of plugins does [[Term -- The Witness|The Witness]] run?
?
[[Term -- Rigs|Rig]]-level plugins.
<!--GUID:f6c8bcd37e496-->

<!--MEADOW_SR_GUID:f9ed90d157c44-->


What level of plugins does [[Term -- The Deacon|The Deacon]] run?
?
[[Term -- The Town|Town]]-level plugins.
<!--GUID:a7d9cde48f5a7-->

<!--MEADOW_SR_GUID:42db3a75a0967-->


What is the concern with long-running [[Term -- Patrol|Patrol]] steps?
?
They interfere with [[Term -- Town Mail|Town Mail]], the cooperative, mail-based eventing system.
<!--GUID:b8eadef59a6b8-->

<!--MEADOW_SR_GUID:aeaeacde6f51e-->


How does [[Term -- The Deacon|The Deacon]] avoid having long-running [[Term -- Patrol|Patrol]] steps?
?
He hands them off to [[Term -- Dogs|Dogs]] to do.
<!--GUID:c9fbefa6ab7c9-->

<!--MEADOW_SR_GUID:424ad7634ad5d-->

---

**Next section:** [[spaced repetition prompts - blog section 13 - Gas Town Plugins|section 13 - Gas Town Plugins]]

---

#flashcards/gas-town/section-12--patrols
