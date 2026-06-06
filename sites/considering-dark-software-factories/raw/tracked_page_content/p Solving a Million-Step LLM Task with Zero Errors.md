https://arxiv.org/pdf/2511.09030

### The takeaway

Their solution of [[decomposing work into narrowly scoped work leads to better reliability]] 

### The Paper

The models have a persistent error rate that prevents scale-up: for instance, recent experiments in the [[performance benchmark -- Towers of Hanoi]] benchmark domain showed that the process inevitably becomes derailed after at most a few hundred steps.
...
[[compounding error]]... which is why [[dim - task horizon length -- shorter]]
:
Thus, although LLM research is often still benchmarked on tasks with relatively few dependent logical steps, there is increasing attention on the ability (or inability) of LLMs to perform long range tasks. This paper describes MAKER, the first system that successfully solves a task with over one million LLM steps with zero errors, and, in principle, scales far beyond this level.
:
The approach relies on an extreme decomposition of a task into subtasks, each of which can be tackled by focused microagents.
...
[[decomposing work into narrowly scoped work]] [[focused task]]s