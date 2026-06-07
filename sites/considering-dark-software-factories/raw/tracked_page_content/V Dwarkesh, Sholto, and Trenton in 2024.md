https://youtu.be/UTuuTTnjxMQ?si=jqrPgNPaMz0o_5V5

[[person - Dwarkesh Patel]] [[person - Sholto Douglas]] [[person - Trenton Bricken]] [[company - Anthropic]] [[company - Google]]

[[B substack for Dwarkesh and two Anthropic guys]]

At 2:40 [[dim - sample efficiency]]. Also, they say that [[dim - context window length -- long]] is under-hyped because it seems that when you have very long context length and can do something like put the codebase into the context that it's almost like the model coming a generation better. X [[dim - technology generation -- greater]]

At 3:30 [[superhuman performance]] because of [[dim - context window length -- long]].  People are not able to keep 1 million tokens of context for fiddly stuff like a codebase in their head.

At 4:20 the notion of [[in-context learning - ICL]] and the idea that the [[attention mechanism]] is a little bit like [[gradient descent]] on the data in the [[context window]]. The associated paper said something along the lines of you take and iterations of gradient descent and it looks like a layers of in-context learning.

At 5:10 [[in-context learning - ICL]] can be slightly problematic. For example, for [[the value alignment problem]] it's a problem if you do 100 shot learning on the context because it's a bit like [[fine-tuning]] that you have no control over. That could be used for [[jailbreak]]ing, for example.

At 6:00 the idea that you in order to get better at [[long-context task]] you need to train with long context so the model can learn how to effectively learn from the information in the long context X [[dim - context window length -- long]] [[in-context learning - ICL]]

At 7:00 the idea of [[long-horizon tasks]] in which an agent needs to engage with the task for many hours, for example. Is there something related to a model being able to properly work with long context tasks? X [[agentically doing this stuff]] [[dim - task horizon length -- long]] [[performance benchmark -- SWE-Bench]]

At 8:30 [[con - the thing that is limited agent so far is the reliability]] and that we haven't reached enough nines yet. When you get enough nines, suddenly it appears like some new behavior has emerged, even though we were very close already. X [[emergent property]] [[agent]]

At 8:50 when evaluating the performance of the model on coding tasks, you weight it depending on how many times it got it right in some number of tries, for example, you [[up-weight]] if it goes from getting it right one and 100 times to one and 10 times X [[evals]]

At 10:05 you're starting [[new eval]] that test for [[long-horizon tasks]] like sweep something that tests github issues X [[dim - task horizon length -- long]]

The guy talks about how automatable a [[job family]] or a [[task family]] is by being able to see how successfully [[dim - task horizon length]] can be completed. And breaking down work into tasks with those horizons. X [[jobs AKA many tasks, orchestrated]]

At 11:50 this new transformer model in the area of research the [[quadratic]] calculations in attention were dominated by the [[Multilayer Perceptron - MLP]] portion. He calls out a [[person - Sasha Rush]] tweet that shows that in a large model, the attention portion doesn't actually take up a huge amount of space as the context gets longer.

At 12:40 when you're actually generating tokens, you have a set of Q vectors that looks up a set of key vectors and it's linear based on the size of the context X 

At 13:00 Dwarkesh ask the question about whether we're moving from most of the learning happening during [[training phase - pre-training]] and [[backpropagation]] to potentially a world where there is a lot more learning happening during the [[forward pass]] during [[inference]].  He asks if [[con - one million token context window]] is actually an intermediate state and the long-term is for much longer context windows, where a lot of the learning happens when processing the context window. X [[in-context learning - ICL]]

At 14:00 the guy draws the analogy of birds and planes and our planes do some things that birds can't do. He thinks that long context might be similar and allow for AI to have a type of memory capability that people don't have. X [[con - people and computers reason differently]]

At 14:30 [[person - Sholto Douglas]] has used the term [[metaleaning]] a couple of times and describes it as something that became emergent in GPT-3 if you provided enough context, it was able to learn from the context you provided. X [[in-context learning - ICL]]

At 15:30 [[con - you get more forward passes by having more tokens]] x [[dim - number of forward passes -- more]] 

At 16:20 when thinking about the ability to use recursion within language empirically, it seems to only go up to 5 to 7 times which seems to align with the 5 to 7 magic number and working memory

At 16:20 Dwarkesh ask how do we differentiate between working memory and reasoning and in particular related to [[dim - context window length -- long]]

At 21:00 The cerebellum has a [[residual connection]].  He makes the point that the cerebellum lights up for lots of different things, and that there is a [[metabolic cost]] associated with it.

At 24:20 most of intelligence is [[pattern matching]] and you can do really good pattern matching if you have [[con - a hierarchical set of associative memories]] [[con - intelligence is pattern matching associations]]

At 25:10 if you he gives example of traversing the alphabet query for a and it gives you be

At 28:00 he explains that in the second layer or maybe it's the second attention head. The value is of the fact is the combination of all of the previous values so in the first layer, it's exactly the values from the values, but in the second layer, it's some combination of things. The other guy says that they might be in different sub spaces.  X The fact that the second layer has all of the stuff mixed together feels related to [[q - can a single layer capture any shape?]]

At 30:00 any chance [[evals]] could use [[unsupervised learning]].  [[con - humans prefer longer answers, even though they might not be better]] which, if the system figured that out and started making longer answers, it would be part of [[reward model hacking]] x [[reward model - RM]]

At 33:00 can [[Artificial general intelligence - AGI]] become much more powerful if they're just doing associations? X [[con - intelligence is pattern matching associations]]

At 34:30 Sholto says that he does think that you could use a system to dramatically speed up [[AI research]] but for the moment we are largely [[compute-bound]].  [[jobs AKA many tasks, orchestrated]] ... Trenton says that it needs more [[dim - reliability]] and [[dim - context window length -- longer]] because the tasks that it's able to do are relatively minimal for the moment.  However, he does think that over the next couple of years it will be able to automate all of his tasks [[diff - AI taking over tasks vs. taking over jobs]] [[con - AI can speed up AI research]] [[con - AI can help with research]]

At 37:20 Dwarkesh makes the point that the AI will not be as good as Trenton at writing new papers just because it can hold the context for all of the modules in memory. Trenton agrees but says that it will speed up the engineering X [[con - there is a big engineering component to research]]

At 38:45 Dash asks doesn't the cost of model training, particularly with evermore, powerful models, dampen the recursive self improvement idea related to the intelligence explosion? [[intelligence explosion]] [[recursive self-improvement]] [[dim - training cost -- higher]]
...
At 39:00 the mental model of the intelligence explosion that we had from 20 years ago was that the recursive self improvement would result in the machines coding themselves better. But now our understanding is that the code is actually very simple and instead it's that it has to train itself

At 41:00 Sholto talks about what he does on a daily basis. First he hast to [[con - prove out ideas of different scales]] you may have a lot of ideas, but you need to pair them down and shot call with imperfect information, and when something goes wrong, you need to understand why, which can be very challenging.  He calls this [[imperfect information]] because it's unclear whether the capability trends will hold at greater scales.  This is necessarily the [[the ai scaling hypothesis]], but even just [[trend line]]s for a specific [[dim - technology generation]] they are working on.  For every very clear trend line that you see in the ultimate papers, there is a [[graveyard]] of bets that didn't pan out as well.  He says that [[intuition]] is incredibly important.

At 44:00 there are two broad classes of problem areas that inform the types of experiments that they want to run in the future. The first is [[grand problems]].  The second is issues that they have bumped into while trying to scale up in the past. X [[scaling problems]]

At 45:00 Sholto keeps coming back to how difficult it is to [[intuit what went wrong]].  Also, he talks about how when the feedback cycle is too slow, you need to have multiple streams running at the same time.

At 46:50 Sholto says that so many of their initial ideas have broken down and so you really need to have simplicity bias and ruthless prioritization.  The best researcher he worked with pull in a lot of different approaches and have a very fast cycle time

At 48:10 Trenton emphasizes how [[empirical]] [[AI research]] is x [[diff - discovered vs. invented]]

At 49:50 the real constraints are compute and the [[taste]] of the researchers x [[intuition]] [[compute-bound]]

At 52:00 one of the big strategic questions is how much compute do you give to scaling the last best thing that you found versus new research?  He says there's a lot to be learned from scaling an idea all the way up because you're not sure if it's going to fall off the [[trend line]] X [[new research]] ... [[loss curve]]

At 53:20 what are ways that [[con - AI can speed up AI research]]?  There's the help with software engineering tasks idea that was talked about before, but Sholto doesn't focus on that.  Instead, he says the perhaps it could help with [[architectural breakthrough]]s or [[synthetic data]] creation

At 55:00 if I wanted to automate a specific field or [[job family]] or understand how at risk it was of automation, having reasoning traces feels like a very important part of that. X [[diff - AI taking over tasks vs. taking over jobs]] [[con - there is reasoning behind why you do the tasks for your job]]

At 56:00 he sort of touches on [[commoditization of AI]] and how important the [[training dataset]] Will be. And also touches on how important it will be for the [[AIs can help curate your training dataset]]

At 57:30 geometry is a good target for reasoning because it's easy to formally define it and verify it. X [[reasoning]] [[con - it is unclear how LLMs reason about math]]

At 59:20 Dash has been skeptical of the idea that more people going into the field would mean faster progress, but Trenton mentions that it's just more shots on goal, even if it is an evolutionary process where some individuals breakthrough isn't quite as important

At 59:30 he brings up [[diff - discovered vs. invented]] and the notion of [[codiscovery]] where the time has come for something because of the adjacencies being there.

At 1:01:40 Dwarkesh asks about whether we will work through the first set of orders of magnitude improvements and scaling, but then hit a wall around GPT-7 after which we can't improve anymore because it's economically infeasible to do so? Sholto suggest that what we get from those orders of magnitude improvements is [[diminishing returns]], but we do get things like [[dim - reliability -- better]] which will cause [[agentically doing this stuff]] to become much more viable.  But yeah, reasoning appears to improve sub linearly X [[orders of magnitude - OOM]] [[Moore’s Law]]  [[sublinear]] [[agent]]

At 1:05:30 he talks about how [[GPT-4]] was probably $100 million, but there could also be a $1 billion run or $10 billion run or even a potential for a $1 trillion run through some nation perhaps [[Government use of AI]] [[dim - training cost -- high]]

At 1:06:00 Trenton suggest that GPT four is maybe 1 trillion parameters and peoples heads are maybe 32 trillion [[dim - number of neurons]]

At 1:07:00 they talk about [[sampling efficiency]] and it seems like they also call that [[dim - data efficiency]]... and Trenton says that has been shown to go up with [[dim - model size -- increase]]

At 1:07:50 Tristan says that the [[interpretability research]] folks think (with their idea of [[superposition]] ) that we are dramatically under-parameterized [[dim - number of neurons -- not-enough]] and that the [[compression]] leads to noise.  Superposition is a compression strategy for dealing with sparsely represented [[training dataset]].  To be able to do interpretability research on that compressed data, you essentially need to be able to return it to high dimensionality and sparsity, which is what they're doing, and then the features become much more obvious than they were in the compressed version where a single neuron firing would fire for many different reasons. X [[q - are models over or under parameterized]]? [[underparameterized]]?

At 1:11:30 [[knowledge distillation - KD]] benefits from getting a probability distribution of what the predicted token is instead of just a [[one-hot encoding]] of the *best* token, which gives you more signal about what you should've predicted.

What is the term that describes when you train a smaller model by using a bigger model's data?::: [[knowledge distillation - KD]]

[01:13:48](https://www.youtube.com/watch?v=UTuuTTnjxMQ#t=1:13:48.35) you can think of [[chain of thought - COT]] as [[adaptive compute]] where you spend more cycles on harder things [[con - an AI should be able to think harder about a harder problem]].  [[dim - number of forward passes -- more]]. [[con - one forward pass implies some finite amount of compute or reasoning]]

[01:14:46](https://www.youtube.com/watch?v=UTuuTTnjxMQ#t=1:14:46.94) the [[residual connection]] is already a compressed [[representation]] X [[compression]]

[01:16:02](https://www.youtube.com/watch?v=UTuuTTnjxMQ#t=1:16:02) one thing that _might_ be smooshed into the [[transformer subpart - key - K]] and [[transformer subpart - value - V]] could be some notion of what the potential _future_ tokens to predict might be. He also talks just a tiny bit about the [[KV cache]]

At 1:16:52 during [[training]] the token that the model predicts is replaced with the _actual_ token.

At 1:17:10 at [[training]] time you do something called [[teacher forcing]] where [[con - telling the model during training what token it _should_ have output]].  [[con - during training the model never sees the token that it output]] ... [[transformer step - training - output]]

At 1:23:00 the idea that maybe chain of thought reasoning would be helped by allowing for something more like a residual connection where you output, the logic as well as the token. X [[abstract representation]] maybe this also plays into what he says several minutes later where he says that we want [[dense representations]]

At 1:24:00 they asked the question about whether we should be trying to orchestrate multiple smaller models, or if there should be one bigger model. The guy suggests that there should be many smaller models that we orchestrate in the short term so that we can first fine-tune the smaller models and second, so we can understand why they are being chosen, but then Overtime maybe we move towards a single model.  X it's not clear to me where this fits in with [[mixture of experts - MoE]]

At 1:26:00 he says that currently there is a big distinction between small models and big models, and also there is this notion of fine-tuning, but with very long context, it's possible that tuning will no longer be necessary. These may be artifacts of where we are right now.

At 1:27:00 he says that you can't train with reinforcement learning unless the client gets some kind of reward. So for example, if you are at an extremely high-level and your goal is to generate blueprints for customers if the customers never like any of the blueprints, then there's no no model Reinforcement learning.  The signal is too sparse

At 1:27:50 Dash mentions that we want [[dense representations]] 

At 1:31:50 the intuition behind why fine-tuning on math makes you better reasoning it is that in math and in programming, you have to pay such careful attention to the position of things, so that likely has some carryover x [[con - fine-tuning on math makes you better at reasoning]]

At 1:33:00 Shomo says modeling code critically helps you model the underlying reasoning of some complex problems that the programmer thought through, but also code is such a structured format.

At 1:35:00 show talk about how in smaller models, you can add in specific things like [[head - induction]]s, but how there is interpretability evidence that shows that in larger models those types of [[circuit]]s are automatically created.

At 1:47:00 the guy said he worked with Gourlay on helped him understand the importance of being good at systems and understanding the systems because the systems directly impact the algorithms x [[hardware-aware algorithmic design]]

At 1:49:00 who talks about a tree of constraints.

At 1:50:00 he talks about how a person who learns every area of the system and doesn't learn it to too much depth, and learn it all at the same time and has high enthusiasm and access to the best teachers Could be very successful 

At 1:52:00 he talks about repair programming with [[person - Sergey Brin]] and how there is a surprising alpha with going to the office every day.

At 2:08:50 he asked if there is some reasonable [[dim - number of dimensions]] for embedding that makes sense from a neuroscience standpoint, or if not because of [[feature splitting]]

At 2:11:00 defining what a [[ai/ML feature|feature]] is is very difficult.  It's unclear what you should consider a state and how granular something can be.  But then Dash turns around and asks him what a feature is, and he says "it's a directed direction in [[activation space]].  A [[latent variable]] that is operating behind the scenes that has causal influence over the system you're observing

At 2:40:00 he says it's possible that your [[latent space]] of [[representation]]s is [[dense]] and that it's a [[ai/manifold]] instead of being these discrete points.  You could move across this manifold, and there would be some meaningful behavior at each point, and it's much harder than to label things as [[ai/ML feature|features]]

At 2:15:50 you take these features and compose them together into a [[reasoning]] [[circuit]]

At 2:17:00 he says that hopefully using interpretability techniques you would be able to find more general [[circuit]]s

At 2:18:20 he mentions how an [[head - induction]] is a mechanism that copies and paste from an earlier position just by positioning. For example, Mr. and Mrs. Dursley do something… If it says "Mr." next, then Dursley is most likely the next word.  The suggestion is that that's not [[reasoning]], but I'm not sure if they are suggesting that it is a [[circuit]]

At 2:19:00 [[head - induction]]s are a two layer transformer

At 2:20:00 he talks about [[circuit]]s They have seen before.  He calls it an I.O.I circuit, which is an indirect object identification circuit. The example is Mr. and Mrs. Smith go to the store. Mr. Smith gives the object to and then the answer is obviously Mrs. Smith.  If you ablate The circuit then other heads will pick up that same mechanism X [[ablation]]

At 2:20:30 some heads always copy the word before or five before or something like that, but there is another head that is responsible for deciding that it should not copy that.  Lots of circuits performing simple operations, but when they are chained together, you get unique behaviors X are we talking about [[attention head]]s here?  Different [[head]]s?

At 2:20:50 he talks about [[sycophancy]] where the model just tries to tell you what it thinks you want to hear.

At 2:22:30 the notion that you have that a computational neuroscientist would have access to something kitten into alien brain where you can each of the neurons and see what the [[circuit]] are and the [[backup circuit]]s are x [[ablation]]

At 2:23:00 [[automated interpretability]]. Having the models assign [[label]]s. X [[interpretability research]] [[synthetic data]]

At 2:23:50 how do you make [[evals]] for [[super-intelligence]] or [[superhuman performance]]?  The guy said if you buy the [[con - associations all the way down]], you should be able to [[con - make the representations more course grained]] in a way that helps you see the [[reasoning]].  He gives the example of superhuman performance in chess, and how they can interpret that.  You should be able to decompose the behavior into simpler circuits or features to figure out why it did what it did. X [[slang - to "coarse grain" something]]

At 2:24:20 Trenton says we are actively trying to use [[dictionary learning]] on the sleeper agents work now.

At 2:26:00 there's a question of how universal [[ai/ML feature|features]] are across models. [[the quanta theory of neural scaling]] that given the same [[training dataset]] you end up learning the same features in the same order.  Dwarkesh asks then why [[curriculum learning doesn't work]] and he mentions [[the stuff you train on last will have an outsize impact]]
...
[[dim - training data ordering]] [[learning has an order to it]]

At 2:27:50 the idea that a model has a bunch of latent abilities you get better at [[entity recognition]] and [[fine-tuning]] that [[circuit]].

At 2:30:20 in the original paper, there's a little bump in the [[training loss]] when it seems to discover [[head - induction]]s.  It goes off the rails little bit, discovers induction heads, then starts improving again.  He calls this "an incredible piece of retroactive explanatory power"

At 2:32:00 should we worry less about the paperclip maximizerAt 2:32 should we worry less about the paperclip maximizer Because of feature universality?

At 2:33:00 there are three separate [[ai/ML feature|features]] for base 64 encoding because there are so many base 64 encoded URL's in the text from the Internet because of hyperlinks. So there are circuits developed for base 64 decoding. X [[circuit - base64]]

At 2:30:43 one benefit of [[dictionary learning]] over [[linear probes]] is that it's [[unsupervised learning]] x [[interpretability research]]

At 2:37:00 Dwarkesh asks about [[feature splitting]].  The idea is that depending on how [[dim - number of neurons]] you have, you may be able to achieve different amounts of [[dim - feature fidelity]] (Fidelity was my term not theirs).  For example, a [[dim - model size -- small]] might I have a feature for birds, but a [[dim - model size -- large]] would have different features for all of the different species, or even more granular.

At 2:37:30 [[dictionary learning]] happens after you train the model. You give it a bunch of inputs and it projects the activations into a higher dimensional space x [[projection]] [[dim - number of dimensions -- higher]] .  It is [[unsupervised learning]] in that you do not have a set of [[sparse feature]]s in mind, however, you do have to supply it with the inputs. X [[sparse]]

At 2:38:00 If we're looking for [[theory of mind]] features that lead to [[deception]] we could make the inputs be the [[sycophancy]] [[dataset]]
...
interesting that this is neither a [[training dataset]] nor a [[validation dataset]], but some funky interpretability dataset.

At 2:41:00 when doing dictionary learning and projecting into the higher dimensional space, you can start by having your expansion factor be reasonably low to directionally find something like biology versus Antrax. This helps keep the cost initially, then you can search around that. It's like doing a depth first search where you recursively expand on interesting areas

At 2:42:00 The [[project - mixtral]] paper points out that [[con - the experts in mixture of experts are not obviously split]] [[superposition]] means that the neurons are poly-semantic.

At 2:43:00 Shomo asked the question about whether anthrax always goes underneath biology, or if there is a possibility that it might be nested under some higher level feature that doesn't make sense.  [[con - the geometry of features]]

At 2:44:45 Google has a vision transformers paper where they say that the experts breakdown into pretty obvious classes, like one for dogs.  But this could be because vision is much easier to segment than language X so counter to the notion that [[con - the experts in mixture of experts are not obviously split]]

Two 4850 [[superposition]] is a combinatorial code, and Shomo gives the example of how to neurons can represent the X and Y in a two dimensional space and cover all of R2. X [[la - span]]

At 2:50:00 You have [[distributed representation]]s, but you also have features... The field of [[vector symbolic architecture]]s which is part of [[computational neuroscience]].  You put high dimensional vectors in [[superposition]], which means you sum them, and then you get [[variable binding]]

At 2:55:00 there are [[ai/ML feature|features]] across [[layer]]s that give you a [[circuit]]

At 2:56:50 he says that now is a bad time to be asking about how they would ensure that something like GPT seven was not trying to be deceptive because they are actively investing in ASL4 ? which is what GPT seven would be part of.  They have split up into three groups one that's trying to find attention heads, one that's working on scaling up dictionary learning, and one that finding [[circuit]]s

At 3:02:45 The guy talks about how they can determine that the model is doing something that they don't want it to do and then use [[ablation]]s to fix the behavior.  You can have two models debate something, and then automatically make the ablations.  He talks about how important it is that they have a closed system with quick iteration X [[automated interpretability]] [[ablation]] [[using another model to work with a model]]

At 3:04:00 he asked the question of is it possible that with these interpretability and model altering techniques like [[reinforcement learning with human feedback - RLHF]] But even more so [[ablation]] that there are concerns that AI would be too controllable, and that people would use that to their advantage too much? Shomo concedes that is indeed a very serious concern and one of the reasons why they are pushing for so much openness And [[constitutional AI]], etc . Also, they ask, which government are you specifically concerned about. They don't say as much, but I think the implication is that you want a liberal democracy to be in charge of this type of thing as opposed to some totalitarian dictatorship. X [[Government use of AI]]

At 3:04:30 to talk about bus factor, and how many truly important people there are in each of their programs

At 3:06:50 Wen asked about who they're paying attention to, Shomo says that a lot of people look internally these days and that their teams have roadmaps to look out 2 to 3 years. "if it works well, it's probably not being published" . Shomo wishes that there was more academic work being done in [[interpretability research]] Because it can be done for much lower cost and is much more aligned with basic scientific principles and fundamentals, as opposed to capabilities research requires being able to test things at scale seems more aligned with industry [[dim - research openness -- lower]] [[slang - interp]]
