https://youtu.be/am_oeAoUhew?si=vvWiUkWRhdzwEeB6

[[harness engineering]] [[company - OpenAI]] by the guy who wrote [[b OpenAI harness engineering 2026-02]]
### Summary

As the commentators on the YouTube video point out, he is <span class="link-not-tracked">link not tracked</span> with his <span class="link-not-tracked">link not tracked</span>.  That doesn't mean there isn't a lot of merit to what he is saying.

I take the key points to be:

Roughly, he is systematically <span class="link-not-tracked">link not tracked</span> by identifying [[structured failure modes]] and translating them into [[mechanisms for making agents more reliable]]

By having <span class="link-not-tracked">link not tracked</span>, it allows the system to run [[dim - task horizon length -- longer|autonomously for longer]].

[[AI can make software better and not just faster]], like [[person - Simon Willison]] says.

<span class="link-not-tracked">link not tracked</span>. Treat those areas as [[structured failure modes]].

Tactical suggestion: [[practice - custom linting rules that inject in-repo documentation as context]]



### Notes

At 5:10 it is not just human attention that is scarce but also <span class="link-not-tracked">link not tracked</span>

At 7:00 <span class="link-not-tracked">link not tracked</span>

At 7:30 writing things in ways that is native to the agents and structuring them in a way that is respectful of the fact that <span class="link-not-tracked">link not tracked</span>

At 8:00 there's a meta epistemological question around <span class="link-not-tracked">link not tracked</span>. We spend years as software engineers learning how to make a code that is flexible, maintainable, reliable, that your teammates can build on top of. The code accrues leverage over time.
:
Software engineers have a lot of understanding of what the [[non-functional]] requirements of a successful systems look like.

At 11:30 auto compaction has gotten significantly better and so context people don't start new as much and so context gets paged out, so you have to figure out a way of ensuring that the context remains
...
It sounds like he's saying that we don't need [[Ralph loop]]s as much, anymore, but on the flip-side he says we should be mindful that <span class="link-not-tracked">link not tracked</span>.

At 13:00 he talks about adding <span class="link-not-tracked">link not tracked</span>s that catch specific issues.  For example, on every request, it should always have <span class="link-not-tracked">link not tracked</span>
:
Another <span class="link-not-tracked">link not tracked</span> check that he suggests is forcing all of the files to be less than 350 lines because <span class="link-not-tracked">link not tracked</span>.  Feels like the types of constraints you would add with <span class="link-not-tracked">link not tracked</span>

At 14:30 If you provide context In error messages that will act as prompts.  that can help a lot. For example, there should be no unknown in the middle of the code base because you <span class="link-not-tracked">link not tracked</span> <span class="link-not-tracked">link not tracked</span> using <span class="link-not-tracked">link not tracked</span>

At 15:30 the increases in capability that we see are pretty much the combination of the models improving and prompts. Lots of things are prompts. [[agent skill]]s are prompts.  The error lint results are prompts.

At 25:30 he talks about the process of letting the agent try to accomplish the functional requirements and then once it's done with that, having the system enforce the sort of nonfunctional requirements around code structure or testing philosophy
...
<span class="link-not-tracked">link not tracked</span> which is a different phase

At 28:40 he describes the [[practice - context right in the repo]] documentation inside of the project and get hub as sort of a <span class="link-not-tracked">link not tracked</span> thing.

At 34:45 they sort of pushed towards something like <span class="link-not-tracked">link not tracked</span> and used <span class="link-not-tracked">link not tracked</span>s to ensure that the services were actually being used.  He says that it's great if you can just look into one directory to be able to make most of the changes that you need to make in order to do what you need to do.

Add 35:20 it's critically important that you have one way of doing things. So for example, you should have one programming language, and you should have one way of doing bounded concurrency and you should have one way of doing some other thing and by doing that.  One <span class="link-not-tracked">link not tracked</span>

At 36:30 somebody asked the question about how do you automate code review and he says that you need to start from the idea that he should <span class="link-not-tracked">link not tracked</span>
:
At 37:10 they realize they were spending a lot of time on <span class="link-not-tracked">link not tracked</span>s.  One reason was that they were working on the same code a lot, so that was one of the pushes to <span class="link-not-tracked">link not tracked</span> so there would be greater <span class="link-not-tracked">link not tracked</span>.
:
Add 37:20 the reason why another reason why they were merge conflicts is because PR's stayed open too long. And that's because they required code review so they were waiting on people.

At 37:50 garbage day was Friday where they would look at every piece of slop that made it difficult to merge the PR in the last week and essentially categorize them like [[structured failure modes]], and resolve those.
:
At 38:20 how do you prompt inject the agent when it exhibits this bad behavior

At 38:30 One purpose of the [[practice - context right in the repo]] is that it serves as a centralized way to prompt inject the model for any of the sort of the [[structured failure modes]] (like <span class="link-not-tracked">link not tracked</span> or <span class="link-not-tracked">link not tracked</span> violations)
:
At 38:50 he had them bucket their feedback into the <span class="link-not-tracked">link not tracked</span> that they were operating as for example, front end engineer.

At 40:30 he doesn't use plan mode and believes that he is set up the system in such a way that it should be able to successfully complete tickets without plan mode. He doesn't read the plans.
...
<span class="link-not-tracked">link not tracked</span>
...
On reflection, I realize that I read plans because I don't trust two things: That the model will understand my intent, or that it will translate my intent into a structure that I will agree with.  I realize that both of these could be addressed in a different way. Some people have taken to using a [[agent skill -- grill me]] skill to ensure that the model understands their intent.  They suggest that they are getting much better results because of it.  Another way of ensuring that the model will understand your intent is for your intent, to be clearly described at a higher level in the [[practice - context right in the repo]].  And secondly, if I have carefully specified architectural guidelines and guard rails, and have a very good testing infrastructure, then I should be less concerned that the model will structure things according to my desires.  
...
I've been hearing about people <span class="link-not-tracked">link not tracked</span>, but I had a loose mental model that plan mode sort of forced the agent to think more thoroughly before it would actually implement, leading to better results. It's pretty clear that if you are not forcing plan mode to facilitate a manual review that simply using it to force the model to thank harder as part of a multi step process is an <span class="link-not-tracked">link not tracked</span> that will be <span class="link-not-tracked">link not tracked</span> soon enough, if not already.

At 40:40 earlier, he was asked how he splits his token usage and he says that he spends 30% of it in CI. That's interesting to me because he says that your senior engineers are typically very good at giving reviews and so he wants to level up the agents to be more like the senior engineers so they need to be able to give good reviews. I think the thing that's surprising about that to me is that it's done at CI time as opposed to being done as part of the end of the feature development, but maybe that's an arbitrary distinction. He makes the point that since code is no longer the hard part and it can be generated quickly really the challenge is i'm getting that code into the main line so that the value is actually realized.

At 41:50 someone asks <span class="link-not-tracked">link not tracked</span>
...
Makes me think of [[spec-driven development - SDD]] and the <span class="link-not-tracked">link not tracked</span> hypothesis
:
At 42:20 all of the context that we provide are essentially constraints and optimization passes about which code is acceptable to be included.  Pretty similar to the <span class="link-not-tracked">link not tracked</span> and optimization passes in <span class="link-not-tracked">link not tracked</span>
