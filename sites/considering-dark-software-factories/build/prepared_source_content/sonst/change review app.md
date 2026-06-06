Since the big problem is [[bottleneck - human reviewers]], you want to make [[dim - review ease -- higher]].  You should think of this [[change review app]] as _everything_ needed to make it super easy for the person to approve or provide feedback.

Why an app?  Because of the level of interactivity that the reviewer would benefit from.  And it's a pro tool, so could be mostly keyboard driven, even.

This _app_ is the representation of the change.  [[breakthrough that comes from a better representation]]

### How do people see this review app?

I'm being a little vague here, since I'm a solo-developer at this point and don't use PRs, but in a traditional setup these reviews _could_ be associated with [[pull request - PR]], but also if you do a lot of iterative development, that might be a little late.  I don't see why it couldn't be available at the end of every agent iteration.

### What does the app contain?

A text-based description of the changes

For changes with UI, a [[agent-generated artifact for human review -- video showing changes|video showing UI before and after]] and also the full gallery of the other feature videos for comparison.  Perhaps each test scenario has [[time travelable application state data]] 

A [[development environment playground]] where the user can play with the thing, look at the code if they want to, and even make tweaks to try something different (which in-turn creates _another_ review packet, ultimate).  A [[User Acceptance Test - UAT]] that walks them through what to test

Maybe [[putting your coding agent threads in your PRs|the agent thread]], so they can see the reasoning behind it

[[documentation context graph -- document]] (basically the original spec that motivated the change) with the change areas highlighted.  Perhaps like [[t coginitive debt reduction visualization]]

[[cognitive debt]] reduction artifacts like an architectural change walkthrough ([[architectural visualization]]) or even, perhaps, [[spaced repetition]] prompts that the person could decide to pull into their retrieval practice.

Speculative merge (and rebase) results.  If the tests had been run on master _right_ now, would they pass?  (On reason why [[fast CI]] is a good idea)

---
  
_Loosely referred to as [[proof of work]] in [[project - Symphony]]_