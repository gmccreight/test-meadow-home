^ [[spaced repetition prompts]] - blog section 8 - Talking to your Dead Ancestors

---

## [[Blog Post -- Section 8 - Talking to your Dead Ancestors]]


What problem does [[Term -- Seance|Seance]] solve?
?
Workers often fail to properly hand off work to successors — the new worker spins up and can't find what the predecessor left. Manually finding the right old session among dozens was awkward and almost not worth it.
<!--GUID:984d3e012f2f2-->

<!--MEADOW_SR_GUID:deaffb6b72a89-->


What Claude Code feature does [[Term -- Seance|Seance]] use under the hood?
?
`/resume`, which lets you restart old sessions that were killed.
<!--GUID:187136c6fa296-->

<!--MEADOW_SR_GUID:884de68c01cc1-->


What does [[Term -- Seance|Seance]] actually do when invoked?
?
It spins up Claude Code in a subprocess, uses `/resume` to revive the predecessor, and asks it where the handoff materials are.
<!--GUID:4f1e6929ce382-->

<!--MEADOW_SR_GUID:e72c8d5d02f4b-->


Why doesn't the content of a [[Term -- GUPP Nudge|GUPP Nudge]] message matter?
?
Agents' prompting is so strict about [[Term -- Gastown Universal Propulsion Principle - GUPP|GUPP]] and their role in Gas Town that they ignore whatever you type — unless you directly override their [[Term -- Hook|Hook]] instructions.
<!--GUID:d0413cd98752f-->

<!--MEADOW_SR_GUID:c5e65ffdd98a6-->


How are `/resume` session titles made discoverable?
?
The [[Term -- GUPP Nudge|nudge]] includes the Claude Code `session_id` along with the Gas Town role and PID, giving each resumed session a unique, searchable title.
<!--GUID:f250dcc8b8a29-->

<!--MEADOW_SR_GUID:93244db914b75-->


---

**Next section:** [[spaced repetition prompts - blog section 9 - Molecular Expression of Work (MEOW)|section 9 - Molecular Expression of Work (MEOW)]]

---

#flashcards/gas-town/section-8--talking-to-your-dead-ancestors
