^ meadow [[parallel development]]

---

***Note**: this is written as if if already happened so that when the coding changes are complete I can simply remove this line and the rest will be accurate documentation describing how the system works.*

Meadow supports <span class="link-not-tracked">link not tracked</span>, where the [[developer]] can run different <span class="link-not-tracked">link not tracked</span>s of the meadow development environment in different directories at the same time and they don't conflict (which supports [[git worktree]]s, as well).

In order to support parallel development, there were several challenges we needed to address:

* we use many services that underpin the app, and they run on ports, and those ports will potentially conflict unless they have <span class="link-not-tracked">link not tracked</span>
* In <span class="link-not-tracked">link not tracked</span> (or as the actual production application), we have standard directories that we use for configuration and logs that would conflict. When running in <span class="link-not-tracked">link not tracked</span>, for each <span class="link-not-tracked">link not tracked</span> we'll need to make those directories temporary, and distinct from each other.  They are:
	* The <span class="link-not-tracked">link not tracked</span>
	* <span class="link-not-tracked">link not tracked</span>
* We interact with the <span class="link-not-tracked">link not tracked</span> via our <span class="link-not-tracked">link not tracked</span>s, which store their state in <span class="link-not-tracked">link not tracked</span>.  We have a <span class="link-not-tracked">link not tracked</span> that runs the <span class="link-not-tracked">link not tracked</span>s (and the <span class="link-not-tracked">link not tracked</span> stuff) in the cloud... but there is only one version of that.
	* To support parallel development we run the <span class="link-not-tracked">link not tracked</span>s via <span class="link-not-tracked">link not tracked</span>, and have them interact with <span class="link-not-tracked">link not tracked</span>.  Like the other services, they have <span class="link-not-tracked">link not tracked</span>

With the need to support <span class="link-not-tracked">link not tracked</span> the service discovery is somewhat complicated.  We centralize the service discovery logic into two files:
* <span class="link-not-tracked">link not tracked</span>
* <span class="link-not-tracked">link not tracked</span>

The local one is created by a <span class="link-not-tracked">link not tracked</span>.

*Note: the affordances for <span class="link-not-tracked">link not tracked</span> also help support <span class="link-not-tracked">link not tracked</span>.*