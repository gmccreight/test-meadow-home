https://x.com/rahulj51/status/2029793437793558983?s=20

[[best place for the description of work]]

Unless you can afford to auto-merge PRs without a human review (and regulatory controls). But that requires a massively different level of effort - auto triaging the pull requests and a functioning suite of tests (fast & non-flaky with >70% coverage).
:
Triaging PRs is non-trivial for a complex codebase. A good classification system would look at hotspots, blast radius, architectural complexity etc., all of which are hard to measure and we don't have good tools for these.
...
[[no human -- code review]] [[auto-merging PRs]]

Also counter intuitively, testing remains a somewhat ignored part of the AI SDLC. We may feel a false sense of confidence by adding 1000s of agent-generated unit tests but high velocity code changes need reliable integration tests because most systems fail at the seams. And tools like playwright etc are woefully slow and brittle for this purpose. They were barely helpful in traditional sdlc. But with today's speed of writing code, they are horribly slow.
...
[[integration test]] [[project - Playwright]]
...
Why is it that will spend an insane amount of compute on AI but Lynch Wen spending it on running integration tests?

There is a reason why even the most AI forward teams are dusting off their old copies of design principle books this month. This is not out of disillusionment or existential angst or a resistance to change.
...
[[emphasis on design principles]]
:
It's more that as we sober up from the post holiday euphoria of how the new models can now do long horizon tasks more autonomously, many of us are now witnessing these bottlenecks and trying to find our way out.
...
[[cost disease]]