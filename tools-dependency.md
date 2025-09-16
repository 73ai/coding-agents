# Tool Dependency and the Engine Under the Hood

While coding agents seem simple on the surface—an LLM taking a user prompt, running in a loop, and calling tools—the reality is much more subtle. The key to their performance lies in the **tools they have access to** and how well the LLM is trained to use them.

## Core Tools for Coding Agents

The most crucial tools for a coding agent are:

* **Read File:** The ability to read files and bring their content into the model's context. This often involves a search tool like `grep` or `ripgrep` to find relevant files first.
* **Change Files:** The ability to write changes back to files on disk.
* **Execute Commands:** The ability to run shell commands. This is vital for tasks like compiling code, running linters, or executing tests to see if a change works.
* **Web Search:** The ability to search the web for information.

## Model Training and Tool Integration

To enhance their effectiveness in coding agent loops, models have been trained with specific tools in mind. The effectiveness of these tools isn't just about their presence; it's about how the underlying LLM was **trained to understand them**.

For example, recent Anthropic models like the Claude family (Opus and Sonnet) have been specifically trained on tools such as `bash`, `code_execution`, `text_editor`, and `web_search`. Their documentation explicitly outlines what they can do, creating a strong link between the agent's behavior and the model it uses.

Some models integrate tools directly into their inference layer without requiring agent intervention for tool calls. For instance, certain OpenAI models include an inherent search tool. Even if you don't explicitly provide a search tool, some models might try to call a tool named "search" even if the agent doesn't provide it, leading to a poorer experience if the agent isn't configured to handle that.

## Tool Alignment and Performance

This is a primary reason why an agent's performance can vary wildly depending on which model it uses. Coding agents that support swapping between different models may not necessarily align tools perfectly with prompts, tool naming conventions, or the tools provided to those models.

Coding agents that align the model with system prompts and tool usage outperform those that do not. A good foundation model has been trained with knowledge of what a tool is and how to use it, creating a strong link between the agent's behavior and the model it uses.