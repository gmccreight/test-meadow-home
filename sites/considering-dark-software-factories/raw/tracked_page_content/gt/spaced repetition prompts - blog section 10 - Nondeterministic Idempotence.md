^ [[spaced repetition prompts]] - blog section 10 - Nondeterministic Idempotence

---

## [[Blog Post -- Section 10 - Nondeterministic Idempotence]]


How does [[Nondeterministic Idempotence - NDI|NDI]] differ from Temporal's approach to durable execution?
?
Temporal uses deterministic, durable replay. Gas Town achieves durability and [[guaranteed execution]] through completely different, nondeterministic machinery.
<!--SR:!2026-04-09,4,270-->

<!--MEADOW_SR_GUID:e9d5aa6eb80f0-->


What makes [[Term -- Molecule|Molecule]] workflows computationally complete?
?
They can have complex shapes, loops, and [[Term -- Gate state|gate]]s — making them Turing-complete.
<!--SR:!2026-04-06,1,230-->

<!--MEADOW_SR_GUID:54058814d621d-->


Why are agents less likely to make mistakes when following [[Term -- Molecule|Molecule]]s?
?
They're not managing their own TODO list — they only handle a single, small step at a time, with acceptance criteria already specified.
...
Similar to a [[Ralph loop]]
<!--SR:!2026-04-09,4,270-->

<!--MEADOW_SR_GUID:31a631ca2975b-->


What motivates agents to diligently check off [[Term -- Molecule|Molecule]] steps, even trivial ones?
?
They understand the bureaucracy updates a live [[activity feed]] and puts work on a permanent ledger.
<!--SR:!2026-04-06,1,230-->

<!--MEADOW_SR_GUID:294fb4b8ac847-->
<!--GUID:294fb4b8ac847-->

<!--MEADOW_SR_GUID:8198274e4e5b8-->


What three things make molecular workflows durable in Gas Town?
?
All three are [[project - Beads|Bead]]s backed by Git: (1) the [[Term -- Agent|agent]], (2) the [[Term -- Hook|hook]], (3) the [[Term -- Molecule|molecule]] itself.
<!--SR:!2026-04-06,1,230-->

<!--MEADOW_SR_GUID:0a574fd8fd8ee-->
<!--GUID:0a574fd8fd8ee-->

<!--MEADOW_SR_GUID:5ecfd120df0f7-->


What happens when a new [[Term -- Session|session]] discovers the previous one crashed mid-step in a [[Term -- Molecule|Molecule]]?
?
It figures out the right fix, performs it, and moves on to the next step.
<!--SR:!2026-04-09,4,270-->

<!--MEADOW_SR_GUID:561606fd89e0d-->
<!--GUID:561606fd89e0d-->

<!--MEADOW_SR_GUID:7fb3285683ace-->


What does "nondeterministic" mean in [[Nondeterministic Idempotence - NDI|NDI]]?
?
The path taken is fully nondeterministic — agents may take different routes or even make mistakes — but the outcome is the same.
<!--SR:!2026-04-08,3,250-->

<!--MEADOW_SR_GUID:b80b5a30d7c6d-->
<!--GUID:b80b5a30d7c6d-->

<!--MEADOW_SR_GUID:dd316ff4b4286-->


What does "idempotent" mean in [[Nondeterministic Idempotence - NDI|NDI]]?
?
The workflow eventually finishes with the intended outcome, "guaranteed," as long as you keep throwing [[Term -- Agent|agent]]s at it.
<!--SR:!2026-04-09,4,270-->

<!--MEADOW_SR_GUID:3902cf5b9f511-->
<!--GUID:3902cf5b9f511-->

<!--MEADOW_SR_GUID:3769b89d08585-->


How do [[Molecule acceptance criteria]] enable self-correction?
?
If an agent makes a mistake, it can self-correct because the molecule's acceptance criteria specify what "done" looks like for each step.
<!--GUID:b6c7dc29ca972-->

<!--MEADOW_SR_GUID:0b09404c05c82-->

---

**Next section:** [[spaced repetition prompts - blog section 11 - Wisps - Ephemeral Orchestration Beads|section 11 - Wisps - Ephemeral Orchestration Beads]]

---

#flashcards/gas-town/section-10--nondeterministic-idempotence
