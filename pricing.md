# Pricing and Cost Analysis

## The Hidden Complexity of Costs

The perceived cost of an agent can be misleading. While some models may have a cheaper per-token price than others, the true cost equation is much more complex. The ultimate cost is a combination of:
- Token price per model
- Number of tokens used
- Number of turns it takes to complete a task
- Overall efficiency of the agent loop

For example, while some models are significantly cheaper per token, they might use many more tokens and many more turns to achieve the same result. This negates some of the savings from the cheaper per-token cost due to a less efficient agent loop.

## Current Market Subsidization

There is subsidization happening right now, either from model providers or VC-funded coding agent provider companies. The current pricing may not reflect the true long-term costs.

One founder recently mentioned that they underestimated how many people would get thousands of dollars of value from a $200 subscription. There's pressure to increase rate limits, but the economics are challenging. This has led some to explore **open-source models** as an alternative.

## Self-Hosting vs Managed Services

Hosting your own model is often significantly more expensive than using a hosted model. When you look at self-hosting:
- It's often more expensive to get those tokens than to buy them on platforms like OpenRouter
- Your experience might not be as good because even some open-weight models require significant hacks to self-host reliably
- Tools like **LM Studio** and **Ollama** can help, but there are still many bugs and limitations that make local models less reliable for complex agent tasks

## Token Usage Trends

Providers are working on reducing per-token cost, but token usage is increasing at the same time. Even with lower token prices, we're using many more tokens, and the problems we're throwing at these agents are still constrained by context. So the general expectation is that costs will go up over time.

The number of tokens needed for these tasks will likely increase as we:
- Give agents more context
- Tackle more complex problems
- Require more sophisticated reasoning
- Add more tools and capabilities

This means we can expect the overall cost of using these tools to go up, even if the per-token price remains stable or even falls.