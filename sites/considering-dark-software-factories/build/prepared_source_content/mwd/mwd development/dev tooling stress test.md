This is a parallel stress test of the development tooling to ensure the apps in the worktrees are fully isolated from each other

### Background

[[git worktree]]  based [[parallel development]] is challenging.  The systems that run in each worktree need to be fully isolated (partitioned) from each other, despite running on the same physical machine.   This is true for development and also for testing.  In this document we focus primarily on testing.

We have two types of testing.  Our [[check script]]s do linting and unit tests for the individual parts of the system.  They also invoke some straightforward integrated [[system test]]s that involve a few parts of the system.  Then we also have our [[meadow e2e tests]] that run _everything_: the full "app" code and also the interface with [[meadow cloud -- local]] that act like remote services, but are local  (I could imagine a future version where we allow them to conditionally interface with [[meadow cloud -- remote -- test]] but probably from a serially-running [[CI]] and not from a [[dim - amount of parallelism -- very high]] set of worktrees.

### stress testing parallel testing in multiple worktrees

To ensure that isolation between the worktrees works properly, we need have stress test tooling that creates multiple [[git worktree]]s and then (all at the same time), executes the [[check script]] `--e2e` and `--video` in each worktree.

The stress test is invoked directly from the [[root-level check script]] as `./check --stress -n 5` (the number is optional and if omitted is 3)

### Reports work in parallel, too

Not only do the tests in the [[git worktree]] run in parallel and fully isolated from each other, but their [[meadow e2e tests -- test suite run report]]s are, too. They are partitioned by both the time the report was generated (in the name of the folder... down to the second for a given run) and also by a short worktree identifier.