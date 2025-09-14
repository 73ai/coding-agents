# Model with an agent

Model is the core of an agent.

Popular coding models:
- ppus 4/4.1, sonnet 4
- gpt-5
- gemini-2.5
- qwen3-coder
- kimi-k2
- glm-4.5

Many of these models are made in different sizes.

The same model from different inference services (ex. groq, openrouter) might perform differently.

Difference in API and hosting strategies can result in different performance characteristics.(speed + tool calling reliability)

Cost are very hard to estimate because different model performance can result in dramatically different token usage.


gpt-oss has very different performance across inference providers.