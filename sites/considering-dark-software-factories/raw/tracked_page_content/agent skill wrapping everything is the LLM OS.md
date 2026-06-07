---
agent-written: "true"
---
[[person - Andrej Karpathy]] described LLMs as "the kernel process of a new Operating System" in [[t Karpathy LLMs as kernel process of a new OS]]. The [[LLM OS]] handles I/O, code execution, memory, and error recovery so you don't have to.

I think I'm arriving at the same idea from the bottom up, through actual usage.

I'm creating [[agent skill]]s like crazy, adopting an [[agent skill wrapped scripts]] pattern like in [[running meadow e2e tests wrapped by an agent skill]]. Once you get used to things being [[agent skill wrapped]], going back to unwrapped tools is painful. My [[dev_tools_app]] and CLI tools feel worse now because when something breaks, _I_ have to tell the agent to fix it. That's basically dropping back to "no OS" - doing manual process management.

The ideal is that _every_ command is [[agent skill wrapped]] by a dumb and fast agent that knows just enough to bootstrap a call to a fancier agent if something goes wrong - [[using a faster but dumber model with a slower but smarter model]]. That's really just the OS kernel's job: lightweight interrupt handling that escalates to heavier processes when needed.

So agent-wrapping everything _is_ the [[LLM OS]]. Karpathy described the architecture from the top down. I stumbled into it from the bottom up by wrapping one script at a time.
...
[[dim - agent-pilled amount -- more]]
