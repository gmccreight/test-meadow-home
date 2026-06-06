^ [[design pattern]] - speculative execution

---

Instead of asking the user what to do ([[elicitation]]) and blocking until they respond, the agent should make its best decision, log that decision, and keep going. The user can review and undo decisions later.

This prevents [[agent waiting for user input]]. It's analogous to [[branch prediction]] in CPUs — assume the most likely path, execute [[speculative]]ly, and roll back if wrong.

The key components are:
- A [[decision log]] where the agent records what it decided and why
- An [[undo]] mechanism so the user can reverse any decision they disagree with
- The agent continues working rather than blocking on the user
