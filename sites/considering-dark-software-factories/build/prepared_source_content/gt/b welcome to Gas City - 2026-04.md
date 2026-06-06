https://steve-yegge.medium.com/welcome-to-gas-city-57f564bb3607

SDK for building your own [[dark artifact factory]].

Gas City has deconstructed the entire Gas Town stack into composable, declarative building blocks called [[Term -- pack|pack]]s. You can use these to assemble arbitrary agent topologies, deploy them, sit back, and watch them work from a rich console. _(Or tmux, if that floats your boat. That still works in Gas City!)_
:
[[Term -- Gas City|Gas City]] is the supervisor plane that connects, manages, and coordinates these deployed mini-factories.

[[project - Beads]] all the way down, powered at the base of the stack by a unique git-versioned database called [[project - dolt]].  Dolt was the magic that made our stack run smoothly.

Gas City doesn’t aim to solve all your problems. You will need to wire it to your own [[agent sandbox|sandboxing]], MCP servers, and so on. But it provides you with a rock-solid and easy-to-use foundation to build on: one with a Discord community with thousands of active members.

A dark factory is any system in which coding agents are set up to work autonomously without humans watching. The name is frankly a little bit misleading. It just means background work. It’s only dark inside a dark factory because the work is happening in rooms where there are no humans present. But those rooms are allowed to have windows. Observability is a choice in dark factory design.
...
[[dark factories have windows for observability]]

So then is Claude Code a dark factory? The terminology here, with factories and harnesses and so on, is all evolving fast, so there aren’t any reliable definitions yet. But Claude Code did not start life as a dark factory, because you were generally supposed to watch it while it works. It’s making overtures in that direction with subagents and agent teams, but they keep the lights off intentionally, presumably because it’s a consumer-facing product and it keeps it simpler.
:
Gas City takes a different approach: all agent workers are equally visible and addressable. The lights are on. Normally for the ephemeral [[Term -- Polecats|Polecat]] workers, you don’t bother looking at them. But unlike with coding-agent subagents, if you want to talk to your polecats, you absolutely can.
......
[[Is Claude Code a dark factory?]] [[dim - observability -- higher]]

And so far, Gas City is the only dark factory that has been designed with the goal of creating other factories. The lights are 100% on when you’re working with the Mayor and Crew in Gas City, and you can dial them up as needed in the back rooms with the polecats and dogs. For this reason I have begun to think of Gas City as a Light Factory… or at least, a very well-lit dark one!

At first, dark factories were only used for writing code faster. They focused on the software development process, and basically replaced IDEs. And that’s still primarily how they are used today. I do see some shops making good headway into CI/CD pipelines and peripheral business processes. But dark factories are headed towards handling infrastructure, operations, and even core business processes.
:
Gas Town users soon realized that you could use Gas Town’s stack to create standalone orchestrators that had nothing to do with writing code. Gene Kim and I have talked to companies that are doing this, and I’ve also started myself. Running my online game Wyvern requires a bunch of routine maintenance that goes way beyond CI/CD.
...
[[dark artifact factory]]s

In the very near future, devs will become shepherds, tending flocks of agents which do the ground-level work. It’s not really a manager job, because the workers are not humans; a coding agent’s cat doesn’t get sick and need to go to the vet in the middle of a sev-1 outage. But agentic workers do make human-like mistakes, and they respond well to being managed like people, by and large. They don’t need management. But they need guidance. Shepherding. Keeping-on-rails. That’s the new role for human builders and operators.

After you deploy your first real one, you officially have a garden you’re tending. A tiny crew of agents, acting like employees. Your little factory team runs 24x7, which requires maintenance. You now have to keep it running, manage upgrades and patches, rotate the logs, and of course make sure it’s doing its job. But you don’t have to do the work yourself anymore! So it’s still a huge automation improvement… as long as you can keep it reliable.
...
[[dim - reliability]]

You should almost never deploy a single-agent pack for a real business process. The reality is that any agent can go temporarily insane, at any time, and make a bad call. No matter how smart they are. We know now that hallucinations and false memories and forgetting are baked mathematically into all memory systems; there’s no avoiding it. So you should never just have one coding agent managing a piece of infrastructure. Not even for a low-stakes part of your business. You should always have at least two or three working together on a little crew.
...
[[agent problem - a single agent by itself cannot be trusted to reliably perform its job]]
:
This is exactly why [[dark artifact factory|dark factories]] are so attractive. With [[Term -- Gas City|Gas City]] you can build any sort of [[adversarial group structure]] you like, for a team of collaborating agents. They can watch over each other. By catching each other’s mistakes, the agent group reaches a far more reliable consensus and outcomes than you can get from a single agent. That’s why we think of deployed orchestration as being fundamentally made of multi-agent teams: factories. Define your [[Term -- pack|pack]], deploy it, et voila — you are officially on the path to being an AI-native shop.
...
This helps answer the question: [[what is an AI company?]]

For my game’s player custom-image uploader, images are submitted via a website form, so it starts with an agent that wakes up on a [[Term -- Hook|hook]] and does the work. Then a second agent checks the first agent’s work. Perhaps the first agent makes a recommendation, and the second agent takes action.

A deployed [[Term -- Gas City|Gas City]] [[Term -- pack|pack]] is an [[AI-native]] [[business process automation]]. Once your pack is running, Gas City’s supervisor agent system will keep it going, even on remote machines.
:
At this point, with one deployment, you are officially at Level 9 on the AI Adoption Chart.

Directly quote from this article in the levels 9-11 in [[Steve Yegge's AI adoption Chart]]

Reliability, friends, is a dial. You choose where to set it. More rounds of review, more backstops, more guardrails, more judges, and you can get agentic workers to be as reliable as you need them to be, at least up to some practical ceiling. I wouldn’t use it in situations where you could physically hurt people, e.g. in medical or navigation systems. Not in 2026. But we’ll build our way there, like engineers do, over the next couple of years.
...
[[dim - reliability]] (yep, it's a dial)
...
[[mechanisms for making agents more reliable]]

SaaS is in kind of a funny position right now. If you look at the pyramid from the top, at the SalesForces of the world, it looks like they’re fine, they just need to pivot to make their SaaS sexy to agents. Benioff did that recently with SF, exposing the whole platform headless and API-first, in exactly that: a bid to make SalesForce sexy to agents. That’s the new game for SaaS.
:
People look up there and say, oh it’s gonna be just fine, those are [[system of record|systems of record]], nobody’s going to reimplement them. Nobody wants to pay the tax of maintaining those systems for security, compliance, performance, scalability, etc. Right? This is just the new Buy vs Build.
:
[[Saaspocalypse]] [[diff - buy vs. build]]

Another interesting thing about SaaS is that it grows to become the superset of all the features for all its customers. Over time, most customers gradually recede to using 20% of the SaaS’s features, while subsidizing the remaining 80% for the other customers.
...
[[Saaspocalypse]]

To replace SaaS, you need the unglamorous stuff: declarative deploys, audit trails, version history, identity, and a memory layer that survives the inevitable agent failures. Those are the primitives that make in-housing tractable.
...
Basically you need [[dim - reliability -- high]] and [[dim - observability -- high]]
...
This was what made Gas Town difficult to explain to non-technical people.  It really is like the [[Kubernetes]] of agents, but if you don't understand the value prop of Kubernetes, you won't get the value of Gas Town.  It's not that it's a factory that makes your software, it's that it's a reliable and observable _platform_ for the factory that makes your software.

Most other orchestrators I’ve seen have been able to be super high-ambition. Many lean heavily into the idea that agents, when put together, can just figure stuff out. And to a large extent, they can. But they are intentionally low-control systems. And when they fail, they go off-rails with no audit trail.
...
[[dim - level of control -- low]]

When you express all your work in the MEOW stack, as Beads and Epics (typically harvested from an upstream system like Obsidian), and your agent actions are all recorded in both a database and version history, you wind up with infinitely more control over the outcomes.
...
[[obsidian]]

In enterprises, controlling the outcomes is the holy grail. So I personally wouldn’t use any other orchestrator I’ve seen. They don’t have the federatable, versioned, queryable memory system that Dolt provides. They don’t have MEOW.
...
[[dim - observability -- high]]

Everyone is suffering from tool overload. There are too many tools out there, and nobody can keep up with all of them. My life is so simple in comparison. I never look deeply at any new technology until it reaches a pretty loud public signal threshold. And I almost never have to, because the Gas Town ecosystem has solved so many of my problems.
...
[[those with a good understanding can rise above the noise]]

