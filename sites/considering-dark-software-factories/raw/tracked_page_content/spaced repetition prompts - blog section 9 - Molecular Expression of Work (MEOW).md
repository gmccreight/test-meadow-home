^ [[spaced repetition prompts]] - blog section 9 - Molecular Expression of Work (MEOW)

---

## [[Blog Post -- Section 9 - Molecular Expression of Work (MEOW)]]


Which part of Gas Town does Steve think will outlive the rest?
?
The [[Term -- Molecular Expression of Work - MEOW|MEOW]] stack — the bones underneath Gas Town.
<!--GUID:a3f71c8e29d01-->

<!--MEADOW_SR_GUID:253cc1a0c8e77-->



What do you call a [[Term -- Bead|Bead]] with children?
?
An [[Term -- Epic|Epic]].
<!--GUID:b4e82d9f3a012-->

<!--MEADOW_SR_GUID:a4b0ecbc8c8b5-->



Why are [[Term -- Molecule|Molecule]]s needed when coding agents already break work into TODOs?
?
To set up sequenced work ahead of time, so you can queue hours of work that agents execute atomically in the right order.
<!--GUID:c5f93ea04b123-->

<!--MEADOW_SR_GUID:0ba53aa2704c4-->



What is the key structural difference between [[Term -- Epic|Epic]]s and [[Term -- Molecule|Molecule]]s?
?
[[Term -- Epic|Epic]]s only have children. [[Term -- Molecule|Molecule]]s can have arbitrary shapes.
<!--GUID:d6a04fb15c234-->

<!--MEADOW_SR_GUID:3cde53ad6f073-->



What are the templates used to create workflows in the [[Term -- Molecular Expression of Work - MEOW|MEOW]] stack?
?
[[Term -- Protomolecule|Protomolecule]]s — made of actual [[Term -- Bead|Bead]]s with instructions and dependencies set up in advance.
<!--GUID:e7b15ac26d345-->

<!--MEADOW_SR_GUID:d513ba3aa2eaf-->



What is "cooked" into [[Term -- Protomolecule|Protomolecule]]s?
?
[[Term -- Formula|Formula]]s, written in TOML format.
<!--GUID:f8c26bd37e456-->

<!--MEADOW_SR_GUID:b3e52d0df6913-->



What does "cooking" [[Term -- Formula|Formula]]s into [[Term -- Protomolecule|Protomolecule]]s involve?
?
Macro-expansion of the TOML source to create the protomolecule bead graph.
<!--GUID:09d37ce48f567-->

<!--MEADOW_SR_GUID:ad24cf3ec95dd-->


Are the children of an [[Term -- Epic|Epic]] parallel or sequential by default?
?
Parallel by default. You add explicit dependencies to force sequencing.
<!--GUID:2bf59ea6a1789-->

<!--MEADOW_SR_GUID:92c8a8899d324-->



Why do [[Term -- Molecule|Molecule]]s survive agent crashes, compactions, and restarts?
?
Because a molecule is a chain of [[Term -- Bead|Bead]]s which is stored in Git. A new [[Term -- Session|session]] just finds its place in the molecule and picks up where the last one left off.
<!--GUID:3ca6afb7b289a-->

<!--MEADOW_SR_GUID:195860c3e186d-->



What is [[Term -- guzzoline|guzzoline]]?
?
The big sea of work [[Term -- Molecule|molecule]]s — all molecularized work in the system. It's more of an idiom than a core concept.
<!--GUID:4db7b0c8c39ab-->

<!--MEADOW_SR_GUID:c67ea64c5ce95-->

---

**Next section:** [[spaced repetition prompts - blog section 10 - Nondeterministic Idempotence|section 10 - Nondeterministic Idempotence]]

---

#flashcards/gas-town/section-9--molecular-expression-of-work-meow
