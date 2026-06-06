https://www.anthropic.com/engineering/managed-agents

### Summary

The way I interpret this.  Prior to this, Claude would run code directly in the user's computer, whereas codex runs stuff in [[codex sandbox]] and asks for permissions to run outside it, like I show in [[example - Codex asking to run outside the Codex sandbox]]



### Notes

A running topic on the Engineering Blog is how to build effective agents and design harnesses for long-running work. A common thread across this work is that harnesses encode assumptions about what Claude can’t do on its own. However, those assumptions need to be frequently questioned because they can go stale as models improve.
:
As just one example, in prior work we found that <span class="link-not-tracked">link not tracked</span> would wrap up tasks prematurely as it sensed its context limit approaching—a behavior sometimes called [[context anxiety]] We addressed this by adding context resets to the harness. But when we used the same harness on Claude Opus 4.5, we found that the behavior was gone. The resets had become dead weight.
......
[[the bitter lesson suggests you should try to reduce inductive bias as much as possible]]


Building Managed Agents meant solving an old problem in computing: how to design a system for [[programs as yet unthought of]] Decades ago, operating systems solved this problem by virtualizing hardware into abstractions—process, file—general enough for programs that didn't exist yet. The abstractions outlasted the hardware. The read() command is agnostic as to whether it’s accessing a disk pack from the 1970s or a modern SSD. The abstractions on top stayed stable while the implementations underneath changed freely.
...
[[abstractions that may survive the bitter lesson]]

But by coupling everything into one container, we ran into an old infrastructure problem: we’d adopted a pet. In the pets-vs-cattle analogy, a pet is a named, hand-tended individual you can’t afford to lose, while cattle are interchangeable. In our case, the server became that pet; if a container failed, the session was lost. If a container was unresponsive, we had to nurse it back to health.
...
[[pets vs cattle]]

For custom tools, we support MCP and store OAuth tokens in a secure vault. Claude calls MCP tools via a dedicated proxy; this proxy takes in a token associated with the session. The proxy can then fetch the corresponding credentials from the vault and make the call to the external service. The harness is never made aware of any credentials.
...
[[storing secret credentials in proxies]]

Recovering from harness failure. The harness also became cattle. Because the session log sits outside the harness, nothing in the harness needs to survive a crash. When one fails, a new one can be rebooted with wake(sessionId), use getSession(id) to get back the event log, and resume from the last event. During the agent loop, the harness writes to the session with emitEvent(id, event) in order to keep a durable record of events.
...
[[durable append-only log with separate consumers]]

Long-horizon tasks often exceed the length of Claude’s context window, and the standard ways to address this all involve irreversible decisions about what to keep. We’ve explored these techniques in prior work on context engineering. For example, compaction lets Claude save a summary of its context window and the memory tool lets Claude write context to files, enabling learning across sessions. This can be paired with context trimming, which selectively removes tokens such as old tool results or thinking blocks.
:
But irreversible decisions to selectively retain or discard context can lead to failures. It is difficult to know which tokens the future turns will need. If messages are transformed by a compaction step, the harness removes compacted messages from Claude’s context window, and these are recoverable only if they are stored. Prior work has explored ways to address this by storing context as an object that lives outside the context window. For example, context can be an object in a REPL that the LLM programmatically accesses by writing code to filter or slice it.
:
In Managed Agents, the session provides this same benefit, serving as a context object that lives outside Claude’s context window. But rather than be stored within the sandbox or REPL, context is durably stored in the session log. The interface, getEvents(), allows the brain to interrogate context by selecting positional slices of the event stream. The interface can be used flexibly, allowing the brain to pick up from wherever it last stopped reading, rewinding a few events before a specific moment to see the lead up, or rereading context before a specific action.
:
Any fetched events can also be transformed in the harness before being passed to Claude’s context window. These transformations can be whatever the harness encodes, including context organization to achieve a high prompt cache hit rate and context engineering. We separated the concerns of recoverable context storage in the session and arbitrary context management in the harness because we can’t predict what specific context engineering will be required in future models. The interfaces push that context management into the harness, and only guarantee that the session is durable and available for interrogation.
......
[[durable append-only log with separate consumers]]
......
This reminds me of how in [[Gas Town]] [[Term -- Seance]] reaches back into the session log of an earlier session to read the exact contents when the [[Term -- handoff]] is fumbled.