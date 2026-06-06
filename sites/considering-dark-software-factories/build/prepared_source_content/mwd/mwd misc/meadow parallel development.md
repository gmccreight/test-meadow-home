^ meadow [[parallel development]]

---

***Note**: this is written as if if already happened so that when the coding changes are complete I can simply remove this line and the rest will be accurate documentation describing how the system works.*

Meadow supports [[meadow dev mode -- parallel]], where the [[developer]] can run different [[meadow copy]]s of the meadow development environment in different directories at the same time and they don't conflict (which supports [[git worktree]]s, as well).

In order to support parallel development, there were several challenges we needed to address:

* we use many services that underpin the app, and they run on ports, and those ports will potentially conflict unless they have [[differing ports per meadow worktree copy]]
* In [[meadow dev mode -- standard]] (or as the actual production application), we have standard directories that we use for configuration and logs that would conflict. When running in [[meadow dev mode -- parallel]], for each [[meadow copy]] we'll need to make those directories temporary, and distinct from each other.  They are:
	* The [[meadow home directory]]
	* [[meadow logs directory path - root - HOME slash Library slash Logs slash Meadow]]
* We interact with the [[meadow cloud -- remote]] via our [[Meadow lambda]]s, which store their state in [[AWS DynamoDB]].  We have a [[AWS account -- workload -- Meadow - dev]] that runs the [[Meadow lambda]]s (and the [[AWS DynamoDB]] stuff) in the cloud... but there is only one version of that.
	* To support parallel development we run the [[Meadow lambda]]s via [[AWS SAM]], and have them interact with [[DynamoDB Local]].  Like the other services, they have [[differing ports per meadow worktree copy]]

With the need to support [[differing ports per meadow worktree copy]] the service discovery is somewhat complicated.  We centralize the service discovery logic into two files:
* [[app config folder content -- file - resources yaml]]
* [[app config folder content -- file - resources.local yaml]]

The local one is created by a [[script that generates a new meadow copy]].

*Note: the affordances for [[meadow dev mode -- parallel]] also help support [[meadow CI]].*