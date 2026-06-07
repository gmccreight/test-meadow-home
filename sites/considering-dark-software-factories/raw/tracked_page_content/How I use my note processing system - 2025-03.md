
In this note I describe how I take notes on interesting pieces of media, how I use AI to help me process them.  The tooling is very new.  At the end I reflect on both near and long-term challenges with it.

### Taking notes while walking

[[walking and taking notes]]

I go for a walk and listen to some interesting podcast or youtube video.

In this specific case, the video I was listening to was [[v The church accidentally triggered the industrial revolution]] on [[person - Dwarkesh Patel]]'s Youtube channel.

While I'm listening, I'll stop every once in a while, make note of the time, and dictate what I thought was interesting about what was just said into a note in Obsidian.  I basically follow the [[annotated talk blog format]].

### After the walk

My notes are all in the same vault, and are [[densely linked]].  After the walk, I'll take a look at this new note, and maybe do a little bit of manual linking to other notes.  I might do this in my phone or after I arrive home on my computer.

### Processing with AI

In addition to the manual process, when I'm in front of my computer, I'll also use AI to help me work through the new note.  I'll show you my workflow here.

I wanted to make the process as seamless as possible.

I use a nice tool called [[project - swiftbar]] which allows me to add things to the tabbar at the top of my Mac, so I can just select the command like this:


![[Pasted image 20250315143115.png]]


That runs a shell script that does a couple things.  First, it takes a commit of the current state in the git repo where I keep all my notes.  Then it temporarily disables the automatic commit-and-push script I have running (because we are going to make manual commits while doing the processing).  Second, it opens up Cursor with all the notes that link to the "process" note.

Here you can see Cursor opened the  [[v The church accidentally triggered the industrial revolution]] because it linked to the "process" note:

![[Pasted image 20250315150715.png|800]]



I have a cursor rule called `process.mdc` (shown in the orange highlight below).... it is essentially a prompt that describes exactly how I'd like Cursor to process the attached note.  Here you can see the beginning of how it processes.


![[Pasted image 20250315151532.png|800]]




As the processing gets further along, you can see it is creating some new conceptual notes that are relevant to the main note.  I also try to have it find existing notes and link to them.  The new notes show up in git on the left-hand side.  That's why it was important that the script paused the git processing, earlier, since we want to carefully review this AI-generated content to decide it we want to incorporate it.

![[Pasted image 20250315151747.png|800]]


Here's an example of one of the notes it added

![[Pasted image 20250315152553.png|800]]

With a few manual tweaks, it became the [[con - cultural evolution prerequisites]] which is now in my notes.

After creating all the new notes, the process goes back and updates the main page to add the links to those concepts, like how I've shown in the orange highlight below.

![[Pasted image 20250315152359.png|800]]

Not every change is an improvement, so I have to think carefully about whether to accept the AI-suggested changes or not.

Additionally, one way to review things is to open Obsidian itself and browse around a bit and see how it feels, add new pages, re-arrange things, etc.

Once I feel good about the session, I can either walk away and everything will be committed and pushed when the automated system kicks back in about an hour later, or I can manually commit the changes if I want to give them a nice commit message.

### Reflection - Problems

There are some problems with this approach.

#### Problem 1: AI doesn't follow directions perfectly

First, the AI doesn't always follow the directions very well.  It can be frustrating that you've given it very clear instructions, but it simply won't format things the way you prefer, for example.

Sometimes it just deletes things you thought were interesting.

I suspect that with some prompt engineering effort, I could guide it towards marginally less objectionable behavior.

And then there's the whole notion that models are improving quickly and pretty soon it will follow directions better, so this may be a short-term pain.

#### Problem 2: If AI introduces ideas, can I assume cognitive ownership of them?

I'm not talking about legal "ownership" here, I'm talking about whether I fully grok the idea in a way that it makes sense to include it in my notes.  If I'm using [[writing to think]], I don't want to outsource my thinking in a way that I don't actually learn the material!

For example, I wouldn't just pull a whole wikipedia article into my notes and think "yep, I fully grok all that and will remember it forever".  So, is it ok to pull in several paragraphs of AI-generated content, like we did for [[con - cultural evolution prerequisites]] ?

I've considered the topic in [[cognitive ownership]] and [[ownership over the ideas in your notes]], and I _think_ the answer is "it depends"; the length and complexity of the material matters.  So does the level of consideration you gave it, and whether you'll bump into it again soon (is it [[densely linked]])?  Of course, you can pull in a short quote that resonated from AI (or from another person) and [[Recontextualization|recontextualize]] it in your own notes.

This isn't really an AI-specific problem, though.  In [[what makes me convinced people would pull from other people's notes?]] I basically consider the same problem, but if the notes were created by other people, like they would be in a [[federated wiki]].  Or when potentially pulling in ideas from tweets, which is actually pretty compelling because [[tweets are the perfect size for assimilation]].  So, yeah, it's not really an AI question, but rather a question around the benefits and drawbacks of [[keeping externally-generated material directly in your notes]].  But if something as subtle as the distinction between hand-writing your notes vs. typing them impacts [[dim - assimilation depth]]... [[hand written notes help students perform better than typed ones]], then I can only imagine the gap between notes written by yourself and written by someone or something else would be significantly larger.

Another, slightly different angle on this is spaced repetition prompts. Like tweets, they are little conceptual nuggets, but formatted to trigger recall.  There is a related notion that [[writing your own prompts may be more beneficial than using canned ones]].  There has been pushback on that idea from some serious practitioners, though.  In [[t Dwarkesh custom spaced repetition card creation tooling]], [[person - Dwarkesh Patel]] feels that the process of creating the cards is often rote.  In [[my hacker news comment about canned prompts]] I detail [[person - Andy Matuschak]] and [[person - Michael Nielsen]]'s  evolving thoughts on the topic, where they seem to think that the process of generating high quality prompts is *so hard to do well*, that a person could benefit from having an expert create the cards for them.
...
Note: I broke this into it's own page [[do you need to write your own spaced repetition prompts?]]

edit 2025-04-26: as I think about it more [[Wikipedia's talk pages]] [[exposing chains of thought in the UI]] and [[meta context]].  A friend of mine mentioned how [[notes live in a liminal space between the world and your mind]].  That's true, and these notes that you didn't write yourself are even further from being truly assimilated. It's like there's a spectrum of [[dim - assimilation depth]].  Going forward I think [[tools for thought]] will need to embrace this [[meta context]] as a first class concern.

edit 2025-06-16: I have noticed that a compact conceptual size can alter how I take notes on media as well.  For example, I might take much more dense notes on a short video like [[v deflationary AI]] because it doesn't feel quite as overwhelming as trying to take dense notes for some massively long podcast like [[V Dwarkesh, Sholto, and Trenton in 2024]]

edit 2026-01-19: The idea of how [[you need mental alignment when working with coding agents]], and how that's similar to this concept of needing to [[assimilation|assimilate]] the ideas that a [[connected note]]s agent puts into your notes.

### Reflection - why do I do this?

I'm honestly not sure.  I used to [[Coke can collection|collect Coke cans as a kid]].  Maybe I'm just a [[collector]] at heart.  I like [[thinking in concepts]] and collecting and mulling over ideas.  I've heard advice that you should [[keep questions and problems in mind]] so as you learn new things, you can see if they might apply to moving those problems forward.  These small, [[atomic]], [[densely linked]] notes feel like a bunch of little problems to keep in mind.

But also, I like sharing ideas with people.  I think it's fun to pull people in to discuss the ideas --- to give scrutiny to ideas in a [[chat - dialectic]] process.  Making concepts into notes, like [[Andy's working note about evergreen notes|evergreen notes]] makes them feel more real, and makes me more enthusiastic to embrace [[actively seeking out disconfirming information]], because there's something I can _do_ with that disconfirming information.  It also makes them easily shareable, as I do in this doc.

Stepping _way_ back... maybe externalizing the ideas also insulates me from identifying too closely with them... because I know they're all up for debate.  Maybe that helps me not get too emotionally attached to anything specific... I'm not sure.  I do know that I tend to get very excited by pushback on the ideas I share, because that pushback helps me move the idea towards something that hopefully maps to reality better.  For example, since I shared this document, originally, I've gotten pushback on the idea of [[cognitive ownership]] (can you really _own_ these ideas?) and the role that notes play in [[assimilation]]... so now that's one of my open problems.

### About this note

This note (along with all the links in it) was published from Obsidian to a microsite using the nascent "Meadow" framework.  If you're interested, check out Meadow here: [[Introducing Meadow]]

### Concepts

[[using AI to find or create conceptual notes]]
