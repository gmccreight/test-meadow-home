https://factory.strongdm.ai/

[[company - StrongDM]]

The narrative form is included below. If you'd prefer to work from [[first principles]], I offer a few constraints & guidelines that, applied iteratively, will accelerate any team toward the same intuitions, convictions, and ultimately a factory of your own. In kōan or mantra form:
:
- Why am I doing this? (implied: the model should be doing this instead)
:
In rule form:
:
- Code **must not be** written by humans
- Code **must not be** reviewed by humans
:
Finally, in practical form:
:
- If you haven't spent at least **$1,000 on tokens today** per human engineer, your software factory has room for improvement


Together with YOLO mode, the updated model from Anthropic provided the first glimmer of what we now refer to internally as **non-interactive** development or **grown** software.

One recurring theme of the agentic moment: we need new language. For example, the word "test" has proven insufficient and ambiguous. A test, stored in the codebase, can be lazily rewritten to match the code. The code could be rewritten to trivially pass the test.
:
We repurposed the word **scenario** to represent an end-to-end "user story", often stored outside the codebase (similar to a "holdout" set in model training), which could be intuitively understood and flexibly validated by an LLM.
......
[[validation naming is hard]]

Because much of the software we grow itself has an agentic component, we transitioned from boolean definitions of success ("the test suite is green") to a probabilistic and empirical one. We use the term **satisfaction** to quantify this validation: of all the observed trajectories through all the scenarios, what fraction of them likely satisfy the user?
...
not a [[binary pass or fail evaluation]] but rather a more loose definition.

