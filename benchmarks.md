# Agent Benchmarking and Evaluation Challenges

## Why Quality Is So Hard to Evaluate

It's incredibly hard to evaluate the quality of an agent, even those using the same model. This puts us in an unfortunate situation where traditional metrics don't tell the whole story.

When we see benchmarks like **SWE-BENCH**, we see a bunch of numbers. But these numbers alone don't capture the full picture. There's also the possibility of "benchmark optimization," where a tool is inadvertently tweaked to perform well on a specific test without improving its general capabilities. A lot of this optimization might be happening during the RL stage of model training.

## Key Evaluation Factors

Some critical factors that benchmarks often miss:

1. **Token usage:** How many tokens does it use?
2. **Turn efficiency:** How many turns does it take to complete a task?
3. **Tool performance:** How slow are the tools that it uses?
4. **Think vs execute time:** How much time does it spend in thinking rather than executing?
5. **Parallelization capability:** How much can it parallelize?
6. **Error recovery:** Does the agent get stuck and never recover?
7. **Safety checks:** Are pre-flight and post-flight checks in place?
8. **Real-world robustness:** Has it been "battle-tested" for autonomous use?

## The Complexity of Speed and Efficiency

There is benefit from one-shotting the result because you're less likely to go into iteration which might be slow. Recently, some models increased the context window to 1M, which hugely benefits one-shotting instances.

While iterative improvements and consistently running the right tools can lead to better code quality over time, some models tend to produce incorrect code initially. However, their eagerness to execute tools often results in faster refinement and better-looking code compared to others.

It's also tricky to estimate costs. Just because a token is cheaper doesn't mean you'll save money. While services might be faster, that doesn't help if they're also worse. Sometimes, being faster doesn't matter if the time to the first token is higher. It is really, really hard to evaluate.

## The Need for Real-World Testing

Public benchmarks can give you some numbers, but they don't capture the full picture of safety, reliability, and real-world performance. What prevents people from using a tool isn't always the code quality; sometimes, it's something as annoying as a bad user interface.

What we need is more practical results and experiences. We need to share more genuine experiences that describe what people actually did with these tools and what works and what doesn't.

## Overall Challenges

- It's very hard to evaluate coding agents today
- You are much more likely to find attachment to a tool people already use than unbiased experience reports
- Tool/Model relationship makes it harder to evaluate the quality of agents
- Just because multiple agents use the same model doesn't mean they have the same prompts or the same tools
- Just because an agent's TUI looks good doesn't mean that it performs well
- Traditional benchmarking doesn't help enough

The sheer number of agents is overwhelming, and it's unsustainable to have so many of them. They'll have to consolidate down eventually. This makes it even more important to have good evaluation methods and share genuine, long-form experiences with these tools.