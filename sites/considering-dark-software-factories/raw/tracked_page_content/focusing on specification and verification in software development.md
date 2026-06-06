As [[agentic coding]] improves, it is starting to write the majority of application code.  The bottleneck to launching new application features is becoming less about the time it takes to write the code, and more about people's ability to describe what they want, and to verify that the results are what they expected.  That process takes time, and has (so far) been mostly immune to AI automation.  As AI coding improves, a greater percentage of our time will be devoted to app specification and verification, so I think it makes sense to carefully consider how we can do it better.

### App Specification

[[person - Bret Taylor]] and [[person - Michael Truell]] have talked about the [[future of code]] having some kind of [[pseudo-code layer on top of the code]].  Some way of working at a [[dim - level of abstraction -- high|high level of abstraction]].

One thing that might work is [[densely linked]] and carefully structured markdown files that align with the underlying code.

It is pretty clear that the coding agents will also start to take over a larger portion of bulldozing the specification layer as well. To do that they need access to the specs, and to work effectively with a person there needs to be a very clear review mechanism. So, I think these high-level specifications will be treated a lot like code, and they will be pushed forward through conversations and simplifying lenses.
### App Verification

***Rough notes that need to be cleaned up***

What to do about the combinatorial explosion?  

modifying the _real_ data in place (doesn't mock things)

Selenium is problematic (slow, brittle, combinatorial explosion because so high-level)

I've gone back and forth on the amount of test coverage that makes sense.  Especially in [[system test]]s you can have a [[combinatorial explosion]] of conditional cases.  With AI, it is easier to add tests, but if the tests aren't very carefully considered, then this is just another case where it is hard to manage the AI generated _test_ code.  So I think the system tests are a _very_ high leverage place to spend your time.
...
[[AI-enabled coding generates a huge amount of code]]

But also, [[vibe coding]] has dramatically lowered the cost of [[custom developer tooling]], so building custom [[QA tooling]] that is built to make exploring the space of application conditionals as _easy as possible_ is important.

It can also be very helpful to spend time and effort on seeing how _data_ changes.

Find myself [[considering testing]] all over again.

Strongly-typed languages help a lot, and the checking is really fast.

Perhaps [[deterministic simulation]] can help

Very carefully setting up example data that exercises edge cases clearly and can be loaded into the app.  This is part of QA tooling, too.
:
Given the care given to those examples, they should _also_ power your [[system test]]s and perhaps also your [[unit test]]s

### Misc Ideas

That thing where you should use objects for high level stuff and functional coding for low level stuff... AI is _great_ at the functional low level stuff... but you should be defining your objects (or types)
...
Related to [[functional core, imperative shell]]