^ [[Meadow]] [[time travelable application state data]]

---

The most ideal version of this is one or more [[code repo]]s that we commit to while running the scenario ideally by [[snapshotting state at meaningful times in the test lifecycle]], then in the [[meadow e2e tests -- test suite run report review tool -- per scenario]] tooling we can [[checkout the most recent commit of the time travelable application state data from before the current time]]

#### Meadow home

[[meadow home directory]]

Applicable concepts:
* [[files paths are constrained into the worktree when using worktrees]]

The equivalent of `~/Library/Application Support/Meadow/MeadowHome` that is used by the distribution app, but within the [[git worktree]], since running in the worktree overrides the configuration so it sticks within the worktree.  That state is already versioned by a [[native_utils -- fast_git_ops]], so we should take advantage of that.

#### Meadow logs

[[meadow logs directory path]]

Applicable concepts:
* [[files paths are constrained into the worktree when using worktrees]]
* [[you can see changes in a file by copying it over and over to a repo and committing to the repo after the copy]]

#### Dynamo DB Local

[[DynamoDB Local]]

Applicable concepts:
* [[you can see changes in a file by copying it over and over to a repo and committing to the repo after the copy]]

This local Dynamo state could be exported as yaml on every change, then we could do: [[you can see changes in a file by copying it over and over to a repo and committing to the repo after the copy]]

#### S3 local state

[[S3 Local]]

Applicable concepts:
* [[you can see changes in a file by copying it over and over to a repo and committing to the repo after the copy]]

Listing turned into a file. Then we can do this:  [[you can see changes in a file by copying it over and over to a repo and committing to the repo after the copy]]
