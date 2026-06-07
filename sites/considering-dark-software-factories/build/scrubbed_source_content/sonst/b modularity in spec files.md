https://codespeak.dev/blog/modularity-20260309

<span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>

---

The `import` directive
:
Notice the [[markdown extension -- front matter]] at the top of `main.cs.md`:
:
```
---
import storage.cs.md
---
```
:
This tells CodeSpeak that `main.cs.md` depends on `storage.cs.md`. When building `main.cs.md`, CodeSpeak will first build the storage spec, and then build the main spec with full knowledge of what storage provides.
:
You can import multiple specs, and imports are transitive — if A imports B and B imports C, CodeSpeak will build all three in the right order.
......
<span class="link-not-tracked">link not tracked</span>
......
[[app specification will be done with agents and markdown]]
...
[[YAML frontmatter enables dependency-aware specifications]]

That's it — one line changed. The main spec stays exactly the same, because it doesn't care _how_ memos are stored. It only cares that storage exists and provides certain capabilities. This is the payoff of splitting specs: changes to one concern don't ripple into unrelated specs, making them easier to review and reason about.
...
<span class="link-not-tracked">link not tracked</span>
...
[[code-associated specification file]]