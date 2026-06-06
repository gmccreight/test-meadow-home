https://youtu.be/_2NijXqBESI?si=Sp0hSVhoJC5kvmvk

[[person - Jim Fan]]

[[physical AI]] [[RL learning environment]]

### Summary

It's really hard to get the training data at the scale needed for robotics.  So researcher rely on [[simulation]] with [[domain randomization]] to increase the scale of the data they can train on.  That itself is nothing new.  But recently they've started using LLMs that generate XML to create randomized layouts of realistic environments, then they are also using Midjourney-like [[video diffusion model]]s to make those highly varied layouts much more realistic.  The end result is [[RL learning environment]]s that are varied and realistic enough that they drive [[dim - transfer strength -- strong]], and the robots can successfully accomplish the tasks in the real world.

### questions

It's not actually clear to me how he motivates the name of the talk. What specifically is "the physical Turing test"? Is it the fact that people were surprised by the example video being a simulation?

How is the data that they need for this different from the data for self driving cars? Is it that there are so many more variations in how the world presents itself for general humanoid robots versus the types of configurations that you see of streets and vehicles on streets?  Another difference is that with enough foresight you can gather a huge amount of training data from cars through cameras and sensors on Howell. People are driving them. There's nothing in alias for humanoid robots, except perhaps glasses in the future. But it was already common for people to drive around in cars and very few people wear the special glasses.

The other thing is that people have been working on making high fidelity driving games for so many years.

Even if you have great simulation for driving, you need the ability to accumulate lots of real world, examples of cases. For example [[example - self driving - bike rack with bike on back of car]]

Self driving is in a two dimensional space which makes it less complicated.

Also, [[the whole body control problem]] seems a lot harder than controlling a car, since for example, the car only has steering and acceleration, whereas a [[humanoid robot]] has so many [[actuator]]s

It's not clear to me if the end result of this process is to provide high fidelity life like examples that are Video like and highly buried, or whether it also places the simulated robot into such varied situations as well. For example, does it create these generated environments in real time And have the robot operate in them in simulation?  That feels like it would be a much more true [[evaluation environment]] where the robot could get benefit from [[reinforcement learning - RL]]

Is real time good enough? Yes, I think it is if you can also do it highly parallel. So either you want it real-time and extremely parallel or extremely fast and not has parallel either one works.


### Before Watching

Maybe this video will be about [[evaluation environment]]s?

### Media Notes

Mentions [[b we passed the Turing test and nobody noticed]]

The physical [[Turing test]]

At 2:40 [[person - Ilya Sutskever]] said [[the Internet is the fossil fuel for AI]] and that we're running out

At 3:50 human fuel is worse than fossil fuel.

At 4:20 [[simulation]] reminds me of [[automatic domain randomization - ADR]] from [[B robot-hand-rubiks-cube]].  Ah, yes, he mentions that!
:
At 5:30 the [[simulation principle]], in which you train 1 million times and the real world version is the 1,000,001 example, states that the physical world is [[in-distribution - ID]] of the training.  He talks about a [[digital twin]] environment and then  [[transfer performance]]
...
[[digital twin]] feels a bit like the [[evaluation environment]] I was expecting.

At 6:40 it doesn't matter what the embodiment is as long as you have the robot model.

At 6:50 [[the whole body control problem]] of [[humanoid robot]]s is that there are a very large number of [[key point]]s and [[velocity vector]]s

At 7:00 you can [[transfer learning]] the [[dim - number of shots learning -- zero]]

At 7:35 1.5 million parameters is enough to capture the subconscious thinking for motion. The [[System 1 thinking]].
...
[[dim - number of parameters -- lower]]

At 8:00 [[simulation 1.0]] is [[digital twin]].  It can run on a classical [[physics engine]].  But the problem is that you have to create the digital twin.
:
At 8:20 A large scale [[compositional simulation]].  [[layout generation]] using LLMs to generate XML.  [[company - midjourney]] for textures
...
Like [[t adobe project scenic - 3D camping to image]]

At 9:25 one [[human demo]] , [[environment generation]], then [[motion generation]] makes many variations.

At 10:05 Simulation 1.5 - [[digital cousin]] is a slower hybrid [[generative physics engine]].  Slower because it also incorporates generative stuff.
...
Different from [[digital twin]]

At 10:30 Who contrasts the decades of work needed to improve traditional [[physics engine]]s for video games with the amazing progress in the [[video diffusion model]]s... the [[example - Will Smith eating pasta]].  

At 11:00 they take a general purpose video generation model and do [[fine-tuning]] on their [[domain-specific]] lab data to create a [[custom model]] a [[video diffusion model]]

At 12:00 [[simulation 2.0]] is [[digital nomad]] which uses a [[neural physics engine]]

At 14:10 [[vision action language model]] which takes in pixels and language outputs motor controls.