^ challenge - [[edge case callout]]s are hard to manage

---

We have various special app and site states like [[app state -- brand new]] and [[site state -- only the initial site page is tracked]] where [[publisher]]s might be confused about what to do because they are new to the system.  So, we do some [[hand holding]] via [[onboarding]] prompts or callouts.

The challenge is that these are [[edge case]]s that we don't bump into much in day-to-day use.  So how can we ensure that the code and [[app component -- callout]]s behind them continues to work without it being arduous [[meadow manual QA]] all the time?

One way is that [[the dev_tools_app makes testing the edge cases easier]].  They basically make it really easy to get into certain types of application setups.

Another is to directly design for reviewing the [[scenario doc -- callout]]s in a specialized [[meadow e2e tests -- test suite run report review tool]]