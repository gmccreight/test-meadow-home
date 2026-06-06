https://youtu.be/Ve-akpov78Q?si=HDg6UPXTqBDGafC2

### Summary

Large enterprises' codebases are extremely hard to manage because they are huge, interdependent, and often highly varied.  They already grow like weeds, but in the near future, they will grow even faster, thanks to AI-enabled development.  New tools need to be developed to allow the enterprises' staff who work on cross-cutting concerns, to manage that more abstract complexity better.

At a narrow scope, tools like [[company - Cursor]] have shown how AI can aid developers in quickly adding features, but what about when you need something more like a bulldozer, for huge tasks like changing your logging platform, enterprise-wide, across a thousand repos?  For [[horizontal work]] in [[con - large scale code changes]]

This video explores one solution to that problem, a product called [[project - grit]], and goes into the technical details about how it uses massively concurrent forking agentic workflows to solve the problem.  I found the section at 14:00 about the use of [[project - firecracker]] to do fast, exploratory [[hypothesis testing]] (which feels a little like [[beam search]]) to be particularly intriguing.

### Details

[[agent]] [[dim - number of agents -- high]] [[workflow type -- codified workflow with some agentic parts]]

At 1:57 [[AI developer tooling]] the product, [[project - grit]], is aimed at [[raising the ceiling]] instead of [[lowering the floor]].  Basically, it is targeted at top developers to be a very large-scale code bulldozer (vs. helping those who are less familiar with coding be able to make things they would not have been able to).  X Kinda funny because [[software engineers don't want to spend all their time doing code review]] but that's essentially what you'll get with these super-high-leverage system-wide tools.
...
[[con - large scale bulldozer for dealing with AI generated content]]

At 3:20 once more developers start using AI (and the AI becomes more powerful, too) there's gonna be way more code, and we're gonna need tools for managing just tons of code. Rather than single lines, you're gonna be making huge changes across many files. X  [[AI-enabled coding generates a huge amount of code]] [[con - needing to manage huge code bases at higher levels of abstraction]] [[whole-codebase]]

At 8:00 when searching to replace the logging for a whole enterprise across thousands of repos, they use their own special SQL that does both static analysis in concert with using LLMs . X Roughly makes me think of [[neuro-symbolic]] techniques more generally.

At 10:50 the idea that IDEs are already giving us superhuman tools with [[linting]], [[type checking]], etc, and that we need to ensure that we give our LLMs the same tools X [[superhuman performance]]

At 12:50 the iteration time for checking a potential solution is comprised on coming up with a code change in the LLM, then checking the compilation.  In big enterprises, the build time for [[continuous integration - CI]] can be multi-minute, which actually dwarfs the LLM time and kills the iteration time.  You need to make sure that you are using the same language server tools that you would as a person using the IDE... where they do incremental change detection and you get feedback almost immediately instead of relying on your CLI tools that are part of CI (since they are so slow).
...
[[language server]]
...
What you want is [[dim - speed -- fast]] for your [[iteration cycle time]]

At 14:00 he talks about the problem of [[compounding error]]s and how you can get in a bad state that you can't recover from. The solve is to use [[project - firecracker]] to be able to snapshot the memory of a process at a known good state and then try 10 hypothetical changes, then you rely on things like [[unit test]]s, etc. to determine which ones are the best and you establish a [[quorum]] to decide what should become the new base to fork from x [[con - automatically testing AI generated code]] [[con - deciding which branch is the best]]
...
This also reminds be of [[neuro-symbolic]] approaches to reasoning using the [[abduction]] methods.  Basically [[con - generating hypotheses]] [[hypothesis]] then winnowing things down by [[hypothesis testing]].  The difference here is that these seem to be short-term hypotheses and [[branching]] with the aim of getting to some _new_ [[known good]]  [[checkpointing]], then [[forking]] off of that to go further.  That feels a little like [[beam search]].  This is all to avoid the [[compounding error]] (AKA [[error accumulation]]), which is particularly important because of [[dim - reliability -- low]] and a lack of revisiting [[ground truth]].  LLMs doing [[multi-step]] [[inference]] tend to have [[exposure bias]] and [[distribution shift]], which causes the errors to get worse over time.

At 15:50 he talks about how it can get really expensive to do so many forks to your code and edit the whole file in each of the forks because [[output token]] are more expensive than input tokens. Because it's auto regressive. Also the output limits are not growing as fast as the context windows, which have become very large.

At 17:00 he describes the challenges with applying changes. Full file works well, but is very expensive, LLMs are not very good at generating [[ai/diff]]s with good line numbers, etc. so they invented a loose search and replace. X [[con - applying code changes is a specific problem]]

---

[[dim - scale -- high]]