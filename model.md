# Models and Foundation Models

Model is the core of an agent. There are only a handful of models capable of effective coding agent operations at the moment.

## Popular Coding Models

The most significant models for coding agents are:
- **Anthropic models** (Opus 4/4.1, Sonnet 4) - Explicitly trained on specific tools, with strong documentation about their capabilities
- **GPT-5** - Fantastic for code generation, though tool usage patterns vary
- **Gemini 2.5** - Great for code generation, though tool usage hasn't been as strong
- **Open-weight models:**
  - Qwen3-coder
  - Kimi-k2
  - GLM-4.5
  - And a growing number of other models capable of tool calls

Many of these models come in different sizes, and their performance can vary wildly between providers.

## Provider Variations and Performance

The same model from different inference services (ex. Groq, OpenRouter) might perform differently. There are reports of wildly different performance for the same model on different providers on OpenRouter.

Differences in API and hosting strategies can result in different performance characteristics:
- Speed variations
- Tool calling reliability
- Time to first token
- Context handling

Some models have very different performance across inference providers. This makes it extremely difficult to make fair comparisons.

## Model-Agent Alignment

When models launch, some tools that had early access outperform those that only added support on day one. Presumably, the developers who got a heads-up knew how to better match their prompts and tool usage to the model.

For example, when GPT-5 launched, agents that had been specifically tuned for it showed better performance than those that simply swapped it in as a drop-in replacement. This is particularly true for open-ended tools that let you swap out models.

## Open-Source Considerations

While venture capital may be subsidizing costs for some users, this has led many to explore open-source models. However, self-hosting them can be more expensive and difficult than using a managed service:

- Tools like **LM Studio** and **Ollama** can help with local hosting
- There are still many bugs and limitations that make local models less reliable for complex agent tasks
- Even some open-weight models require a lot of hacks to self-host them reliably
- Your experience might not be as good as with managed services

## Cost Estimation Complexity

Costs are very hard to estimate because different model performance can result in dramatically different token usage. While GPT-5 is significantly cheaper per token than Anthropic models, if it uses many more tokens and many more turns, this negates some of the savings from the cheaper per-token cost.

The ultimate cost depends on:
- Token price
- Number of tokens used
- Number of turns required
- Efficiency of the agent loop
- Model's ability to one-shot vs iterate

It's clear there's something really valuable here with these models, and we'll likely see more of them, because it's just so much fun to build with them.