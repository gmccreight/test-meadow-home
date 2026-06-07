https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/

<span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>

Historically, I’ve struggled to find a concise, simple way to explain what it means to practice <span class="link-not-tracked">link not tracked</span>. Too often, when someone asks me “How did you come up with this approach?” I find I can’t give them a satisfying answer. I know it didn’t just come to me in a vision—I have an iterative design process that doesn’t require plucking the “right” approach out of thin air—yet I haven’t been very successful in communicating that process to others.

However, about a month ago, [I was reflecting on Twitter](https://twitter.com/lexi_lambda/status/1182242561655746560) about the differences I experienced parsing JSON in statically- and dynamically-typed languages, and finally, I realized what I was looking for. Now I have a single, snappy slogan that encapsulates what type-driven design means to me, and better yet, it’s only three words long: <span class="link-not-tracked">link not tracked</span>

One of the wonderful things about <span class="link-not-tracked">link not tracked</span>s is that they can make it possible, and sometimes even easy, to answer questions like “is it possible to write this function?” For an extreme example, consider the following Haskell type signature:

This message is helpfully pointing out that our function is _partial_, which is to say it is not defined for all possible inputs. Specifically, it is not defined when the input is `[]`, the empty list. This makes sense, as it isn’t possible to return the first element of a list if the list is empty—there’s no element to return! So, remarkably, we learn this function isn’t possible to implement, either.
...
<span class="link-not-tracked">link not tracked</span>

Let’s look at the original (partial) type signature for `head` again:
:
```haskell
head :: [a] -> a
```
:
The previous section illustrated that we can turn that partial type signature into a total one by weakening the promise made in the return type. However, since we don’t want to do that, there’s only one thing left that can be changed: the argument type (in this case, `[a]`). Instead of weakening the return type, we can _strengthen_ the argument type, eliminating the possibility of `head` ever being called on an empty list in the first place.
:
To do this, we need a type that represents non-empty lists. Fortunately, the existing `NonEmpty` type from `Data.List.NonEmpty` is exactly that. It has the following definition:
:
```haskell
data NonEmpty a = a :| [a]
```
......
<span class="link-not-tracked">link not tracked</span>

Put another way, you can think of a value of type `NonEmpty a` as being like a value of type `[a]`, plus a _proof_ that the list is non-empty.

These two functions elegantly illustrate two different perspectives on the role of a static type system: `validateNonEmpty` obeys the typechecker well enough, but only `parseNonEmpty` takes full advantage of it.
...
[[take full advantage of the typechecker]]

Consider: what is a <span class="link-not-tracked">link not tracked</span>? Really, a parser is just a function that consumes less-structured input and produces more-structured output. By its very nature, a parser is a partial function—some values in the <span class="link-not-tracked">link not tracked</span> do not correspond to any value in the <span class="link-not-tracked">link not tracked</span>—so all parsers must have some notion of failure. Often, the input to a parser is text, but this is by no means a requirement, and `parseNonEmpty` is a perfectly cromulent parser: it parses lists into non-empty lists, signaling failure by terminating the program with an error message.

Under this flexible definition, parsers are an incredibly powerful tool: they allow discharging checks on input up-front, right on the boundary between a program and the outside world, and once those checks have been performed, they never need to be checked again! Haskellers are well-aware of this power, and they use many different types of parsers on a regular basis:
...
[[coding pattern -- guard the edges so you can code within the happy zone]]