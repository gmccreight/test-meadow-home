[[multi site management]], and specifically [[managing changes in the source graph structure over time]] for many sites

[[local code]] and [[local configuration]].  Great for the [[publisher]], but means the [[developer]] need to have very careful [[migration tooling]] to update from any pre-existing app version and configuration.  If we want to have [[plugin support]], we'll need to be very careful about defining careful interfaces, too.
:
Relatedly, in [[html generation]] we have [[hooks config]].  Once we publish those hooks, we will need to support that interface for a _long_ time, so it better be pretty generic (and solid).
:
[[local app challenge -- easy upgrade]]
:
[[local app challenge -- support older versions]]
:
[[local app challenge -- identifying and fixing bugs]]

It is an imperfect problem space with tradeoffs.  We're just drawing an arbitrary border around the [[source graph]] contents.  What to do about [[pulling in a hub source page but it is only partially applicable]] or the pages that are at the [[frontier edge]] and point to pages that are beyond the frontier (so they have a bunch of [[link modification]])

[[challenge - edge case callouts are hard to manage]]
### Once we decide to introduce AI

Figuring out [[where meadow AI should focus]] and how to have it work most effectively with the user.

