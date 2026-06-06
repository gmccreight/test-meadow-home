https://youtu.be/XNtkiQJ49Ps?si=qo24Lw2iiH0Rhptm
### My Summary

When you move...

![[planning reviewing and doing work|500]]

... then your bottlenecks change.

While some domains are seemingly more verifiable than others, if you look at the work in the domain and do [[task decomposition]] on the *actual* work, you'll see that some of those tasks are [[dim - verifiability -- high|easily verifiable]] and other are [[dim - verifiability -- low|hard to verify]].  The easy to verify stuff can be automated, and the hard to verify stuff can rely on people.  You still get a speedup from automation, particularly if the person can do bulk review because the agent does [[design pattern - speculative execution|speculative execution]] then presents the person with a [[decision log]] and the user can [[steerable|steer]], in bulk, later rather than getting pinged for every little decision, which would cause the agent to get stuck [[agent waiting for user input|waiting on user input]])

He also makes the point that [[natural language is a limited UX]].  For a very complex and deep [[tree of tasks]], chat is not a good interface.  You want [[application interface -- internal -- standard UI powered by AI|a standard UI powered by AI]] that surfaces tabular data as a management interface (for that [[bulk human review]]) or documents with annotations for getting more detailed.

### Notes

At 4:00 he talks about the verifiability of different domains, but actually within those domains the individual tasks that are part of the domain have different levels of [[dim - verifiability]]

At 4:00 he talks about the difference between there's two things there's [[dim - level of control]] and [[dim - level of trust]]. Then later he talks about how [[you can increase trust with guardrails]]

At 6:10, he talks about how you can't actually verify a contract in legal, but you can get a proxy for it
...
[[Ways of doing verification in legal domain]]

At 8:00 he describes generating a legal report as essentially a big [[tree of tasks]] or a [[directed acyclic graph - DAG]]
...
That tree of tasks, which needs to be carefully executed makes me think of [[Term -- Molecule|Gas Town molecule]]

At 10:30 [[elicitation]] which is asking users what to do but then instead of doing that you should make a decision and put it in a decision log and then the user can undo that decision later. So the agent doesn't get stuck.
...
[[design pattern - speculative execution]] because we want to avoid [[agent waiting for user input]]

At 11 minutes, he shows a tabular interface for review and also a document.