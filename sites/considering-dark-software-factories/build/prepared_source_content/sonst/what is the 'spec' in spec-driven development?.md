^ What is the 'spec' in [[spec-driven development - SDD]]?

---

First, let's agree that we're talking about specification of complex features, not one-off tasks.  Ok, good!
### How much detail?

There's this trending notion that [[markdown is code]] or maybe [[specs are code]].  Indeed they _can_ be, but [[markdown is code only when it is actually thinly veiled code]], as described in [[b a sufficiently detailed spec is code]].

[[what people mean when they say "spec" is unclear]], but I'll take a stab at a definition that _I_ find useful, here.  It may warrant its own name, to disambiguate it from a generic "spec", but for now I'll just roll with spec.  I don't find pre-describing specifications at that deep level of detail to be compelling for the systems that I am building.  Instead, I prefer my specs to be [[dim - level of abstraction -- high|at a higher level of abstraction]].

So, what's the right level of detail, then?  Perhaps something more akin to what has traditionally been in an ERD.  [[not every detail is described in an ERD]], but many key details are, and I find the level of detail that I've seen in ERDs in the past to be quite compelling for guiding and driving agentic development.

### Don't you need enough detail to drive development?

Somewhere in the process, enough context needs to be given to the coding agent for it to successfully complete its work.  But I wonder whether the specs _need_ to completely specify everything up-front so that a developer is completely out of the loop at implementation time?  That feels like [[Big Design Up Front - BDUF]] with the primary aim being to feed a [[dark software factory]] that can work without further developer involvement.  But, [[Just how dark do dark software factories need to be?]]

I think that question gets at the heart of the matter.  It's just not clear what specification actually _is_.  So far, in my experience doing agentic coding, a reasonable specification has been, essentially, durable and persistent [[Engineering Requirements Doc - ERD|ERD]]-level artifacts that are decomposed into a [[documentation context graph]].  Or, more specifically [[the 'spec' part of a documentation context graph should be at a PRD and light ERD hybrid level]]

To actually complete the coding, I start with those specifications then do a more ephemeral, detailed, and interactive planning phase, then work iteratively with the agent to complete the actual coding.  When complete, that process *can* lead to some updates to the [[documentation context graph]] as a side-effect of the implementation process, but they tend to be pretty high-level updates.  Perhaps we came up with a better name for a folder, or added some additional high-level constraint.

In that approach, the specs alone are clearly not enough.  [[the spec, the exact coding planning phase, and the code are all necessary context for development]]

### Fire-and-forget tasks

Ok, we've been describing complex features, but there are also fire-and-forget tasks, of course.

Those tasks are ideal candidates for a completely dark [[dark software factory]], and in that case the factory _still_ benefits from the context combo of the ERD-like specification and all the code.  In traditional software development there are _a lot_ of those kind of tasks, so being able to almost completely offload them is no small benefit!  But they need to be pretty bounded to be successful, and knowing what will work in that modality is a bit of a judgement call, still, so developers need to manually route things to that system.  Bug fixes, UI tweaks, performance enhancements are all reasonable candidate areas.

### How to structure the specification

In the more traditional [[software development lifecycle - SDLC|software development lifecycle]], the ERD was a standalone document, though, with one or more references back to the [[Product Requirements Doc - PRD|PRD]].  It remained pretty static after the project kicked off, and frequently the code ultimately skewed from both the ERD and the PRD because [[implementation is a learning process]].  That skew and the different audience frequently necessitated a completely new set of documentation to be written *after* the project completion.

I believe that a well factored [[documentation context graph]] is superior way to model that context, and that there are many advantages to storing that [[practice - context right in the repo]].  I think that specs for features should be a [[a PRD-ERD hybrid]] that should be deconstructed into a well-factored [[documentation context graph]] that can help orient the agents and the humans working with the system.  Basically, [[the 'spec' part of a documentation context graph should be at a PRD and light ERD hybrid level]].

If you need a [[linear narrative]] (like perhaps for a project kickoff meeting) have an agent generate a purpose-specific one for you that you can merge with other project management considerations, like sequencing, milestones, etc in order to facilitate the communication in that meeting, but treat that as an ephemeral point-in-time artifact.

Good ERDs re-motivate the problem at a high level, then point back to specific sections of the [[Product Requirements Doc - PRD|PRD]] to motivate portions of the work.  In the [[traditional SDLC]], pointing to the "why" provided critical context to the team doing the actual implementation.  It allowed them to deviate from the ERD's plan more easily if a better approach to solving the underlying problem became clear while doing the implementation.  I believe that context is equally important for agentic implementation.