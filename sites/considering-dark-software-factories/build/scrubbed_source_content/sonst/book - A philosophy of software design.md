page 11 in the conclusion: dependencies, and <span class="link-not-tracked">link not tracked</span> accumulate to cause complexity.  Complexity shows up as change amplification, high cognitive load and (the worst)... unknown unknowns.

Page 20 [[deep module]] an interface should be much simpler than the underlying implementation

Page 29 [[information hiding]]

Page 31 [[information leakage]] you can leak through a wide interface, or by two or more classes having information about something. He suggest that maybe you should move all of the functionality into one class in that case, making it, essentially a deeper module.
...
Related to [[do not repeat yourself - DRY]]

Page 34 <span class="link-not-tracked">link not tracked</span>

Page 41 Arguing for [[somewhat general purpose interface]]s .  Shows specialist API with text class closely tied to UI leads to [[information leakage]] and when you change UI you also have to make changes to the text class.
:
Putting the backspace method in the text class was a <span class="link-not-tracked">link not tracked</span>.  Because the person working on the UI really wants to know exactly what happens when the backspace button is pressed. The fact that they need to go look It up in the text class is an <span class="link-not-tracked">link not tracked</span>

Page 48 separate general purpose and special purpose code. For example there's a history class for undo. That is a general purpose.  How to actually do undo is special purpose, and embedded in the text class.

Page 108 higher level comments are more difficult to write the lower level comments because you must think about the code in a different way. Ask yourself: what is the code trying to do? What is the simplest thing you can say that explains everything in the code? What is the most important thing about this code?
...
[[seems related]] to <span class="link-not-tracked">link not tracked</span> but for <span class="link-not-tracked">link not tracked</span>

Page 109 The first sentence is different: it explains (in high-level terms) why the code is executed. Comments of the form "how do we get here" are very helpful for helping people to understand the code.
...
[[seems related]] to <span class="link-not-tracked">link not tracked</span> where it describes "why was it done?"

Page 134 writing comments first is how you arrive at the best design because it helps you identify good abstractions
...
<span class="link-not-tracked">link not tracked</span>
...
[[seems related]] to <span class="link-not-tracked">link not tracked</span>

