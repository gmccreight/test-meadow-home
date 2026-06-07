https://youtu.be/am_oeAoUhew?si=vvWiUkWRhdzwEeB6

[[harness engineering]] [[company - OpenAI]] by the guy who wrote [[b OpenAI harness engineering 2026-02]]
### Summary

As the commentators on the YouTube video point out, he is [[living in the future]] with his [[dim - token budget -- high]].  That doesn't mean there isn't a lot of merit to what he is saying.

I take the key points to be:

Roughly, he is systematically [[stomping code slop]] by identifying [[structured failure modes]] and translating them into [[mechanisms for making agents more reliable]]

By having [[experienced engineers can codify many non-functional requirements]], it allows the system to run [[dim - task horizon length -- longer|autonomously for longer]].

[[AI can make software better and not just faster]], like [[person - Simon Willison]] says.

[[figure out where you're spending your time and look for ways to spend less time on that]]. Treat those areas as [[structured failure modes]].

Tactical suggestion: [[practice - custom linting rules that inject in-repo documentation as context]]



### Notes

At 5:10 it is not just human attention that is scarce but also [[model attention is scarce]]

At 7:00 [[persona-oriented documentation]]

At 7:30 writing things in ways that is native to the agents and structuring them in a way that is respectful of the fact that [[model attention is scarce]]

At 8:00 there's a meta epistemological question around [[what does it mean to do a good job?]]. We spend years as software engineers learning how to make a code that is flexible, maintainable, reliable, that your teammates can build on top of. The code accrues leverage over time.
:
Software engineers have a lot of understanding of what the [[non-functional]] requirements of a successful systems look like.

At 11:30 auto compaction has gotten significantly better and so context people don't start new as much and so context gets paged out, so you have to figure out a way of ensuring that the context remains
...
It sounds like he's saying that we don't need [[Ralph loop]]s as much, anymore, but on the flip-side he says we should be mindful that [[model attention is scarce]].

At 13:00 he talks about adding [[linting rule]]s that catch specific issues.  For example, on every request, it should always have [[a retry and a timeout]]
:
Another [[static analysis]] check that he suggests is forcing all of the files to be less than 350 lines because [[model attention is scarce]].  Feels like the types of constraints you would add with [[project - Rubocop]]

At 14:30 If you provide context In error messages that will act as prompts.  that can help a lot. For example, there should be no unknown in the middle of the code base because you [[coding pattern -- guard the edges so you can code within the happy zone]] [[Parse, don’t validate]] using [[project - Zod]]

At 15:30 the increases in capability that we see are pretty much the combination of the models improving and prompts. Lots of things are prompts. [[agent skill]]s are prompts.  The error lint results are prompts.

At 25:30 he talks about the process of letting the agent try to accomplish the functional requirements and then once it's done with that, having the system enforce the sort of nonfunctional requirements around code structure or testing philosophy
...
[[t Claude Code stop hook that triggers a Codex code review]] which is a different phase

At 28:40 he describes the [[practice - context right in the repo]] documentation inside of the project and get hub as sort of a [[hub and spoke]] thing.

At 34:45 they sort of pushed towards something like [[microservices]] and used [[linting rule]]s to ensure that the services were actually being used.  He says that it's great if you can just look into one directory to be able to make most of the changes that you need to make in order to do what you need to do.

Add 35:20 it's critically important that you have one way of doing things. So for example, you should have one programming language, and you should have one way of doing bounded concurrency and you should have one way of doing some other thing and by doing that.  One [[object relational mapping - ORM]]

At 36:30 somebody asked the question about how do you automate code review and he says that you need to start from the idea that he should [[figure out where you're spending your time and look for ways to spend less time on that]]
:
At 37:10 they realize they were spending a lot of time on [[merge conflict]]s.  One reason was that they were working on the same code a lot, so that was one of the pushes to [[tree out the code]] so there would be greater [[locality of change]].
:
Add 37:20 the reason why another reason why they were merge conflicts is because PR's stayed open too long. And that's because they required code review so they were waiting on people.

At 37:50 garbage day was Friday where they would look at every piece of slop that made it difficult to merge the PR in the last week and essentially categorize them like [[structured failure modes]], and resolve those.
:
At 38:20 how do you prompt inject the agent when it exhibits this bad behavior

At 38:30 One purpose of the [[practice - context right in the repo]] is that it serves as a centralized way to prompt inject the model for any of the sort of the [[structured failure modes]] (like [[linting rule]] or [[static analysis]] violations)
:
At 38:50 he had them bucket their feedback into the [[persona]] that they were operating as for example, front end engineer.

At 40:30 he doesn't use plan mode and believes that he is set up the system in such a way that it should be able to successfully complete tickets without plan mode. He doesn't read the plans.
...
[[not using plan mode]]
...
On reflection, I realize that I read plans because I don't trust two things: That the model will understand my intent, or that it will translate my intent into a structure that I will agree with.  I realize that both of these could be addressed in a different way. Some people have taken to using a [[agent skill -- grill me]] skill to ensure that the model understands their intent.  They suggest that they are getting much better results because of it.  Another way of ensuring that the model will understand your intent is for your intent, to be clearly described at a higher level in the [[practice - context right in the repo]].  And secondly, if I have carefully specified architectural guidelines and guard rails, and have a very good testing infrastructure, then I should be less concerned that the model will structure things according to my desires.  
...
I've been hearing about people [[not using plan mode|moving away from plan mode]], but I had a loose mental model that plan mode sort of forced the agent to think more thoroughly before it would actually implement, leading to better results. It's pretty clear that if you are not forcing plan mode to facilitate a manual review that simply using it to force the model to thank harder as part of a multi step process is an [[inductive bias]] that will be [[bitter lesson'd]] soon enough, if not already.

At 40:40 earlier, he was asked how he splits his token usage and he says that he spends 30% of it in CI. That's interesting to me because he says that your senior engineers are typically very good at giving reviews and so he wants to level up the agents to be more like the senior engineers so they need to be able to give good reviews. I think the thing that's surprising about that to me is that it's done at CI time as opposed to being done as part of the end of the feature development, but maybe that's an arbitrary distinction. He makes the point that since code is no longer the hard part and it can be generated quickly really the challenge is i'm getting that code into the main line so that the value is actually realized.

At 41:50 someone asks [[is code a disposable build artifact?]]
...
Makes me think of [[spec-driven development - SDD]] and the [[ephemeral software]] hypothesis
:
At 42:20 all of the context that we provide are essentially constraints and optimization passes about which code is acceptable to be included.  Pretty similar to the [[static analysis]] and optimization passes in [[project -llvm]]
