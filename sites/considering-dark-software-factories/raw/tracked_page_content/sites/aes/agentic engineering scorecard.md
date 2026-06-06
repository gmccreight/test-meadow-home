*Skip to the bottom if you just want to see the practices scorecard*

Over the past few months, I’ve gradually converged on a highly iterative style of agentic software development, shying away from the "dark software factory" approach. This post explains why I've made the move, how other agentic engineering practices fit into that model, and which of those practices I’ve personally found useful.

### Motivating the highly iterative process

People [[v agents need more than chat - 2026-04|talk about]] how [[agentic engineering]] causes the [[software development lifecycle - SDLC|software development lifecycle]] to move...

![[planning reviewing and doing work|800]]

... however, in an [[v Github researcher on how we should collaborate with agents in teams - 2026-04|excellent recent talk by a Github researcher]], the speaker argues that we *actually* need to be moving towards a *significantly* more iterative workflow.  She says agents are so fast that people don't want to do the upfront planning work, they just want to dive in and see what they can come up with.  Unfortunately, that means the review stage becomes where people align on the work that should have been done.  She argues that's way too late.

Instead, the alignment should happen much earlier, and iteratively.  Design, planning, and coding (prototyping or real) should blend together into quick iterations that drive the alignment process forward.

That highly iterative process looks more like this:

![[iterative workflow to PR.excalidraw|800]]

In my own work as a solo developer, I don't need to align with others.  Despite that, I have arrived at a similar process after many months of attempting to adopt less iterative, more [[waterfall]]-like workflow.  I tried [[Big Design Up Front - BDUF|big design up front]], where I created a detailed spec then crossed my fingers, hoping that an agent orchestration platform like [[Gas Town]] would crunch for hours without my involvement then kick out a great final product.

It just didn't work out very well.  I found that I wasted too much time trying to get the up-front planning locked in without actually trying stuff out.  Instead I should have been iterating, prototyping, and getting feedback quickly.

In essence, I've found that the [[dark software factory]] process, which I was so excited about in February, just doesn't apply cleanly to the majority of my work.  It does work well for some small subset of my tasks: for example, I can fire off simple bug fixes in parallel or large, functionally-equivalent refactorings.  However, for the majority of my work, the highly iterative design workflow seems to work best, which means that nearly all the time I'm right there in the thread with the agents.

### Improving each thread

Given that I'm in the details of each thread, I have found I can only realistically push a few such threads forward at any given time without becoming tired and confused.  Because of that, I've stopped trying to find the "one true dark software factory" that can execute on numerous threads at once, and instead I'm focusing on finding incremental gains across all the phases of the agentic engineering software development lifecycle that happens within a single thread:

![[phases of the agentic SDLC.excalidraw|800]]

To that end, I've been collecting agentic engineering practices and trying to apply them where they seem to make sense.  There are an *overwhelming* number of new practices appearing in the wild.  I can't adopt them all at once, so I've started mapping them and keeping notes on my level of adoption and where I see opportunities.

Below is a list of those practices and how they map to the phases described above.  I also score my adoption of each practice.  As you can see, there's a lot of red and yellow.  I have a long way to go!

You can click on each practice to see more details about it.

:::meadow
![[agentic engineering scorecard.excalidraw|800]]

enableEmbeddedLinks: true
enableFullscreenButton: true
enableOpenDedicatedPage: false
:::

### For now

I hope this mapping helps orient you as much as it has helped me.

I haven't completely given up on the idea of [[dark software factory|dark software factories]], because "spec-in software-out" is such a compelling vision, but for the moment, this is how I'm getting work done.  In the future, who knows... things are changing fast!

If you have any practices I should know about, please drop me a line at [@gmccreight](https://x.com/gmccreight)

---

I'll update the [[agentic engineering scorecard - changelog|changelog]] with big changes to the practices over time.  I'm incubating new practices in [[agentic engineering practice incubator]]