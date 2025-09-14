# Agent Benchmarking and Eval

It's very hard to evaluate the quality of an agent even those using the same model.

When we see `SWE-BENCH` and other benchmarks, we see a bunch of numbers. but these numbers alone don't tell the whole story. It's essential to evaluate how different agents perform under various conditions.

A lot of benchmark optimization also might be happening during RL stage of model training.

Some factors

1. How many tokens does it use?
2. How many turns does it take to complete a task?
3. How slow are the tools that it uses?
4. How much time does it spend in thinking rather than executing?
5. How much can it parallelize?


There is benefit from oneshotting the result because you're less likely to go into iteration which might be slow. 

Recently sonnet-4 increased the context window to 1M and that hugely benefits oneshotting instances.


While iterative improvements and consistently running the right tools can lead to better code quality over time, some models, like Sonnet, tend to produce incorrect code initially. However, their eagerness to execute tools often results in faster refinement and better-looking code compared to certain versions of GPT-5.



Overall
- It's very hard to evaluate agentic coding tools today
- You are much more likely to find attachment to a tool people already use than unbiased experience reports
-  Tool/Model relationship makes it harder to evaluate the quality of agents
-  Just because multiple agents use sonnet does not mean they have the same prompts or the same tools
-  Just because an agent's TUI looks good does not mean that it performs well
-  Benchmarking does not help