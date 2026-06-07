check scripts are a type of [[validation script]].

There is an executable `./check` script at the root of the project.  It, in turn, calls nested `check` scripts, in sub-directories.  It calls those in parallel, then joins back up.

Each of those sub check scripts runs things like a directory structure check first, then the linter, unit tests, system tests in parallel.  Whatever it makes sense to run in those directories.  If there are any failures, they fail with an error.

The sub-check scripts work independently and can report what went wrong, but also they work with their parent check script which gathers up the information from the lower check scripts and outputs its own higher-level report.  The final output is "OK" (green) or "NOT OK" red.  If it was not ok, it provides the details.

The point of this script is to be a relatively comprehensive local check for broken things that the [[agentic coding|coding agent]] can easily run and get a lot of feedback about whether it broke something.  That way we can encourage it to always run the check script after making its changes.

We try to keep it really fast so that it doesn't impact [[iteration cycle time]], and so a person can also run it whenever they want.

When I fed the above into ChatGPT, it describes this as:

> A composite, hierarchical check system — essentially a local CI gate — where each directory owns an independent check contract and the root orchestrates them in parallel with aggregated reporting.