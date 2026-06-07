^ [[spaced repetition prompts]] - blog section 17 - Comparison to Kubernetes

---

## [[Blog Post -- Section 17 - Comparison to Kubernetes]]


Which roles sit in the [[control plane]]?
?
[[Term -- The Mayor|The Mayor]] and [[Term -- The Deacon|The Deacon]].
<!--GUID:ba570a6969e3e-->

<!--MEADOW_SR_GUID:624882a9b1b02-->


Contrast the three-word descriptions of the purpose of Kubernetes vs. Gas Town.
?
Kubernetes: "Is it running?" Gas Town: "Is it done?"
<!--GUID:1dadcc4b91f50-->

<!--MEADOW_SR_GUID:96e8870586273-->


What does Kubernetes optimize for vs. what does Gas Town optimize for?
?
Kubernetes optimizes for uptime — keep N replicas alive forever. Gas Town optimizes for completion — finish the work, land the [[Term -- Convoy|convoy]], then nuke the worker.
<!--GUID:5790a9e2579be-->

<!--MEADOW_SR_GUID:e178d172544de-->


In Kubernetes, pods are anonymous cattle. What plays the "cattle" role in Gas Town?
?
[[Term -- Session|Sessions]]. [[Term -- Polecats|Polecats]] are credited workers with persistent identities — it's their sessions that are disposable.
<!--GUID:f13b726ee00af-->

<!--MEADOW_SR_GUID:d954fb8567c77-->


What is the Gas Town equivalent of a Kubernetes Node?
?
A [[Term -- Rigs|Rig]].
<!--GUID:152a28596edf8-->

<!--MEADOW_SR_GUID:c9ff3559b85a3-->


What is the Gas Town equivalent of a kubelet?
?
[[Term -- The Witness|The Witness]] — a local agent on each [[Term -- Rigs|Rig]] monitoring ephemeral workers.
<!--GUID:f9d9c49953e96-->

<!--MEADOW_SR_GUID:d439fd754b048-->


What is the Gas Town equivalent of etcd?
?
[[project - Beads|Beads]] — the git-backed source of truth the whole system reconciles against.
<!--GUID:07e9ba48ea6fb-->

<!--MEADOW_SR_GUID:17d3f99589277-->

---

#flashcards/gas-town/section-17--comparison-to-kubernetes
