# Tool Dependency

To enhance their effectiveness in agentic coding loops, models have been trained with specific tools in mind.

For example, recent Anthropic models like the Claude 4 family have been specifically trained on tools such as `bash`, `code_execution`, `text_editor`, and `web_search`.

Some models integrate tools directly into their inference layer without requiring agent intervention for tool calls. For instance, certain OpenAI models include an inherent search tool. Even if you don't explicitly provide a search tool, the `GPT-OSS` model assumes one is available.

That said, coding agents that support swapping between different models may not necessarily align tools perfectly with prompts, tool naming conventions, or the tools provided to those models.

Coding agents that align the model with system prompts and tool usage outperform those that do not.