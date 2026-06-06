^ [[agentic engineering practice]] - [[agentic mutation testing]]

---

### Practice

[[agentic mutation testing]] is basically mutation testing that uses the power of the agent to mutate the code in a way that finds problems.

For example, let's say you have [[practice - custom linting rules that inject in-repo documentation as context|custom linting rules]].  The agentic mutation could do a small code refactor to deliberately violate those rules to prove that your lints actually catch the issue.

Mutation tests can be time-intensive, so tie them into _every_ coding session probably doesn't make sense, but rather you might kick them off as a [[practice - background check]] occasionally.

### Status 🔴

I have only done one of these, but it worked _very_ well.  Status red because one is not nearly enough.



