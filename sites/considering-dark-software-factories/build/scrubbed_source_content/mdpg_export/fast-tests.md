Computers are a <span class="link-not-tracked">link not tracked</span>

What is fast?  No objective answer, but there is one that works for people.  Fast enough that you don't notice it.  That's different for sound than for visual information.

Speed takes and gives.  To achieve it, you have to change how you're doing things.  Once you have it, it changes how *you* do things.  It's transformative.

Speed, in order to be achieved, needs to be the primary goal.

* What you need to change to achieve it
    * decoupling from slow things
        * database
        * GUI

You could mock to get all these things, but that's problematic because of API drift, and the coupling to a specific interface.

* What it gives you?
    * "sub-second tests are a huge enabler of flow, and flow is amazing!" - Katrina Owen from [http://www.youtube.com/watch?v=J4dlF0kcThQ](Therapeutic Refactoring)
    * Since you can run your tests so easily, you run them all the time.  Running them all the time allows you to rely on your computer to tell

Anyone that has used a static language and has fat-fingered something has had the IDE inform them of the mistake immediately, thought "thanks!", and been on their merry way.  There's an opposing, dystopian version of that where you learn about your mistake 5 minutes later, along with several other mistakes, and you're no longer in the code for any of them.  That dystopian vision describes how many of us write and run our tests, primarily because they are slow.

They're slow enough that we feel the need to write more code than we should between each test run, since we don't want to pay the test-run penalty for a small change.  They're slow enough that truly incremental refactoring seems tedious and overkill.  "Let's just use slightly larger refactoring steps so we don't have to run the tests as often!"  I can tell from personal experience that this sometimes results in the refactoring being scrapped with a "git reset --hard" because it got into a state where debugging the problems that arose from one of the larger-than-advisable refactoring steps just wasn't worth it.

I was struck, when I read [Martin Fowler's Refactoring](http://www.amazon.com/Refactoring-Improving-Design-Existing-Code/dp/0201485672) by just *how small* the steps he took were.  Patience is a virtue, but it's a virtue I lack.

---

