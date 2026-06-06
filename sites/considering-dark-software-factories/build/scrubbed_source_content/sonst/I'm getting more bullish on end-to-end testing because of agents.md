### Why I grew to dislike end-to-end tests for UI applications

In my many years coding, I've created a smattering of CLI and mobile apps, but I've mostly developed web applications.

The majority of the applications I've written in my career are web-based, with a 

One of my favorite ways to "learn a lesson" is to [[embrace something a little too enthusiastically, then learn its limitations]]

[[project - selenium]] was flaky



DHH was down on system tests recently after having been very into them.

The [[combinatorial explosion]] problem is still real, and you still want some unit and integration-level tests.


### How we solved for them

We needed [[dim - iteration speed --high|fast iteration speed]] because a human was waiting for the test suite's feedback, And when something broke, they would need to fix it.

To get that quick feedback, we adopted more framework-free tests like [[view model]]s.  They were far faster, and much less flaky.  The problem with the view models was that they still had a problematic seam.  They had to be tied to the actual application somehow.  It was a little bit like the split between [[functional core, imperative shell]] or [[hexagonal-architecture]] or [[clean-architecture]].  Inside the view models you had this beautiful, fast, testable code, but outside was the real world... in the real world matters.  Living in that world, you feel the [[test double drift]].

One of the benefits of lower level tests, for humans, was that when something broke, it could help point you to some specific part of the implementation that was broken. That helped make the fixes faster.  But this is less important with agents. They can always just figure it out from some higher level, broken test.

One of the problems we encountered was that pushing the tests around at scale, often took as long as the bug fix that we were implementing. This was a strong signal that we were ossifying our system in the wrong way.
### non ai improvements

[[project - Playwright]] is faster and less flaky than [[project - selenium]]

Videos

Computers are faster and have greater parallelism

### AI improvements

Temporary flakiness matters less when you can have a background agent ensure non-flaky behavior.

The slow speed matters less when you can have [[project - autoresearch]] drive maximal parallelism and speed.  In practice, I have been able to keep the extensive meadow end to end test suite below one minute in maybe 4 hours of cumulative time spent with an agent on performance optimizations.


### The exact code structure matters less, and so do the unit and low-level integration tests



### architectural opinion matters - in the specification!

[[project - cucumber]] was a very interesting way of describing [[Given-when-then]], but the scaffolding was a real pain to set up and maintain. I find it's often better to try to write code that reads like English then to try to write exactly English. And it's fine if there's a small translation layer between a completely textual, prompt, and and end code that reads well at the level of abstraction that makes sense to the user.

Write the user-facing specs at the [[level of intent]], so a person can easily reason about them.

### How should you specify stuff?

Should it be markdown?  Should it be [[type-safe specification - 2026-02]]?  Should it be some combination?

### A review app

[[agent task -- change review app]]