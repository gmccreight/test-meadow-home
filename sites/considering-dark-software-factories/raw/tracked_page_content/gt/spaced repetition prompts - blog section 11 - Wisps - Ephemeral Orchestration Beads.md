^ [[spaced repetition prompts]] - blog section 11 - Wisps - Ephemeral Orchestration Beads

---

## [[Blog Post -- Section 11 - Wisps - Ephemeral Orchestration Beads]]


What type of [[Term -- Bead|Bead]] is not stored in git, and why?
?
[[Term -- Wisp|Wisps]] are not stored because they describe ephemeral [[Term -- Molecule|Molecules]] of work. Storing them would just be orchestration noise.
<!--GUID:af99ded4f1132-->

<!--MEADOW_SR_GUID:f694bb6cae7ab-->


What type of [[Term -- Molecule|Molecules]] are stored as [[Term -- Wisp|Wisps]], and why?
?
Molecules associated with [[Term -- Patrol|Patrols]] because those workflows need to complete transactionally, but don't need to be stored in git.
<!--GUID:a9638e3fe32e3-->

<!--MEADOW_SR_GUID:4545f2fb30a67-->


What happens to [[Term -- Wisp|Wisps]] at the end of their run?
?
They are "burned" (destroyed). Optionally they can be squashed into a single-line summary/digest that's committed to git.
<!--GUID:0404ba35aa352-->

<!--MEADOW_SR_GUID:7d1028f716fd5-->


How do [[Term -- Wisp|Wisps]] behave while they exist in the database?
?
They get hash IDs and act like regular [[Term -- Bead|Beads]], but are not written to the JSONL file and thus not persisted to Git.
<!--GUID:47ce2fc632346-->

<!--MEADOW_SR_GUID:b507d9744337a-->


In the matter metaphor, what phase do [[Term -- Wisp|Wisps]] represent?
?
The vapor phase — the lightest, most ephemeral form of Gas Town work.
<!--GUID:e92695ddc3eb5-->

<!--MEADOW_SR_GUID:49ef666aa1f67-->

---

**Next section:** [[spaced repetition prompts - blog section 12 - Patrols|section 12 - Patrols]]

---

#flashcards/gas-town/section-11--wisps---ephemeral-orchestration-beads
