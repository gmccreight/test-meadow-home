^ [[Term]] -- Refinery

---

[[Role Class -- Worker|Worker]]
[[Role Class -- Worker -- Rig Level|Rig-level Worker]]

**Refinery**: As soon as you start swarming workers, you run into the Merge Queue (MQ) problem. Your workers get into a monkey knife fight over rebasing/merging and it can get ugly. The baseline can change so much during a swarm that the final workers getting merged are trying to merge against an unrecognizable new head. They may need to completely reimagine their changes and reimplement them. This is the job of the Refinery: the engineer agent responsible for intelligently merging all changes, one at a time, to main. No work can be lost, though it is allowed to escalate.

[[things that run patrols]]