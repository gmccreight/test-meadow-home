^ [[free recall]] -  [[b OpenAI harness engineering 2026-02]]

---

Notes:

* [[b OpenAI harness engineering 2026-02]]
* this free recall
* [[review - Open AI harness blog post - 2026-02-22]]
* [[to remove - Agentic engineering practices - scorecard 2026-04]] (throughout)

---

I read the post a little over a day ago. Here I will try to recall the key ideas.

### The driving principles

#### driving principal 1 - no human involvement

First, and perhaps most importantly, they adopted a principal of [[no human -- coding]], which has deep implications to their approach.  They didn't say this explicitly, but it's not just the _coding_ that they are attempting to remove humans from. They're trying to automate everything around the specification, development, and verification of an app.  So, yeah, [[no human -- code review]] and [[no human -- app verification]], too.  They are even trying to reduce the amount of [[app specification]] that humans must do, too.

#### driving principal 2 - high app legibility for the agent

The second principle was strive for [[dim - legibility -- higher]] for the agent... AKA [[agent legibility]].  This means giving the agent everything it needs to get the job done: [[practice - context right in the repo]] specs right alongside the code, all the logs, [[trace]]s, etc.  it also means keeping the code base structurally legible.  Obvious folders, strict and clear naming conventions, etc.

### QA

for issues that affect the UI they have the agent take short videos before and after, to prove that it fixed it.
...
[[agent-generated artifact for human review -- video showing changes]]

These is the chrome plug-in that drives browser automation the MCP.  I wonder why they don't use playwright?

Off-line sweepers that clean stuff up driven by something like cron

A lot of stuff that they did would normally only get introduced after you have a large development team, but they found that it was very helpful. This is stuff like automating CI, having clear coding standards, etc

Their [[app specification]] lives alongside the code in the repo and uses [[progressive disclosure]], similar to [[agent skill]]s.  Rather than link out to external resources, they attempt to integrate the external resources so that the repo has all the context.  I [[cannot recall]] why the structure their specs exactly like they do.
...
[[coding agent operating without external context]] 

Parallel development with [[git worktree]]s.  Their environment works well with this.  They can spin up multiple versions of the app and it doesn't collide.  This includes the full monitoring stack (logs, 
:
They enforce various in [[invariant]]s, such as that a [[trace span]] can only take up to n seconds.

As a practical matter, they don't worry as much about merge conflicts because the agents can figure it out, but they do find real value in having the tasks partitioned from each other during development.

[[project - ralph wiggum]] like loops. [[cannot recall]] what they are actually using it for

For [[code review]] I believe they have multiple agents attempting to review the code?  I [[cannot recall]] whether they attempted to [[no human -- code review]] yet.  But the before and after videos I mentioned would definitely reduce the amount of time a user would need to review the PR, if they do.

I [[cannot recall]] if they talked about having a command line interface for the app as well. It definitely seems like they're talking about driving it through a lot of [[browser use]], so _maybe_ not?

Perhaps it was this blog post that emphasized [[code interface]]s?  I [[cannot recall]]

I _think_ it may have mentioned [[custom linting rule]]s? [[cannot recall]]
...
On checking, it definitely did.  For things like ensuring the documentation was properly cross-linked

[[keeping the coding agent fed with work]] and 

The whole video before and video after thing makes me think how to a could be automated in the future. I could imagine some sort of L as a judge the judge is the difference is and make sure that they are reasonable, and then something like notebook LLM that manufacturers a Video podcast that showcases the changes and really digs into the improvement