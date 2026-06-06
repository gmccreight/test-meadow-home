https://youtu.be/Ve-akpov78Q?si=HDg6UPXTqBDGafC2

### Summary

Large enterprises' codebases are extremely hard to manage because they are huge, interdependent, and often highly varied.  They already grow like weeds, but in the near future, they will grow even faster, thanks to AI-enabled development.  New tools need to be developed to allow the enterprises' staff who work on cross-cutting concerns, to manage that more abstract complexity better.

At a narrow scope, tools like <span class="link-not-tracked">link not tracked</span> have shown how AI can aid developers in quickly adding features, but what about when you need something more like a bulldozer, for huge tasks like changing your logging platform, enterprise-wide, across a thousand repos?  For <span class="link-not-tracked">link not tracked</span> in <span class="link-not-tracked">link not tracked</span>

This video explores one solution to that problem, a product called <span class="link-not-tracked">link not tracked</span>, and goes into the technical details about how it uses massively concurrent forking agentic workflows to solve the problem.  I found the section at 14:00 about the use of <span class="link-not-tracked">link not tracked</span> to do fast, exploratory <span class="link-not-tracked">link not tracked</span> (which feels a little like <span class="link-not-tracked">link not tracked</span>) to be particularly intriguing.

### Details

[[agent]] [[dim - number of agents -- high]] <span class="link-not-tracked">link not tracked</span>

At 1:57 <span class="link-not-tracked">link not tracked</span> the product, <span class="link-not-tracked">link not tracked</span>, is aimed at <span class="link-not-tracked">link not tracked</span> instead of <span class="link-not-tracked">link not tracked</span>.  Basically, it is targeted at top developers to be a very large-scale code bulldozer (vs. helping those who are less familiar with coding be able to make things they would not have been able to).  X Kinda funny because <span class="link-not-tracked">link not tracked</span> but that's essentially what you'll get with these super-high-leverage system-wide tools.
...
<span class="link-not-tracked">link not tracked</span>

At 3:20 once more developers start using AI (and the AI becomes more powerful, too) there's gonna be way more code, and we're gonna need tools for managing just tons of code. Rather than single lines, you're gonna be making huge changes across many files. X  [[AI-enabled coding generates a huge amount of code]] <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span>

At 8:00 when searching to replace the logging for a whole enterprise across thousands of repos, they use their own special SQL that does both static analysis in concert with using LLMs . X Roughly makes me think of <span class="link-not-tracked">link not tracked</span> techniques more generally.

At 10:50 the idea that IDEs are already giving us superhuman tools with [[linting]], <span class="link-not-tracked">link not tracked</span>, etc, and that we need to ensure that we give our LLMs the same tools X <span class="link-not-tracked">link not tracked</span>

At 12:50 the iteration time for checking a potential solution is comprised on coming up with a code change in the LLM, then checking the compilation.  In big enterprises, the build time for <span class="link-not-tracked">link not tracked</span> can be multi-minute, which actually dwarfs the LLM time and kills the iteration time.  You need to make sure that you are using the same language server tools that you would as a person using the IDE... where they do incremental change detection and you get feedback almost immediately instead of relying on your CLI tools that are part of CI (since they are so slow).
...
<span class="link-not-tracked">link not tracked</span>
...
What you want is [[dim - speed -- fast]] for your <span class="link-not-tracked">link not tracked</span>

At 14:00 he talks about the problem of <span class="link-not-tracked">link not tracked</span>s and how you can get in a bad state that you can't recover from. The solve is to use <span class="link-not-tracked">link not tracked</span> to be able to snapshot the memory of a process at a known good state and then try 10 hypothetical changes, then you rely on things like [[unit test]]s, etc. to determine which ones are the best and you establish a <span class="link-not-tracked">link not tracked</span> to decide what should become the new base to fork from x <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span>
...
This also reminds be of <span class="link-not-tracked">link not tracked</span> approaches to reasoning using the <span class="link-not-tracked">link not tracked</span> methods.  Basically <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span> then winnowing things down by <span class="link-not-tracked">link not tracked</span>.  The difference here is that these seem to be short-term hypotheses and <span class="link-not-tracked">link not tracked</span> with the aim of getting to some _new_ <span class="link-not-tracked">link not tracked</span>  <span class="link-not-tracked">link not tracked</span>, then <span class="link-not-tracked">link not tracked</span> off of that to go further.  That feels a little like <span class="link-not-tracked">link not tracked</span>.  This is all to avoid the <span class="link-not-tracked">link not tracked</span> (AKA <span class="link-not-tracked">link not tracked</span>), which is particularly important because of <span class="link-not-tracked">link not tracked</span> and a lack of revisiting <span class="link-not-tracked">link not tracked</span>.  LLMs doing <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span> tend to have <span class="link-not-tracked">link not tracked</span> and <span class="link-not-tracked">link not tracked</span>, which causes the errors to get worse over time.

At 15:50 he talks about how it can get really expensive to do so many forks to your code and edit the whole file in each of the forks because <span class="link-not-tracked">link not tracked</span> are more expensive than input tokens. Because it's auto regressive. Also the output limits are not growing as fast as the context windows, which have become very large.

At 17:00 he describes the challenges with applying changes. Full file works well, but is very expensive, LLMs are not very good at generating <span class="link-not-tracked">link not tracked</span>s with good line numbers, etc. so they invented a loose search and replace. X <span class="link-not-tracked">link not tracked</span>

---

[[dim - scale -- high]]