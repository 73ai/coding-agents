# Tool Safety

Some agents employ pre-flight and post-flight checks to evaluate tool usage. For example, Claude Code uses the fast haiku model to assess whether a proposed tool is safe to use. Agents that leverage a secondary LLM for sanity checks on tool calls can reduce the risk of inappropriate tool usage.

Implementing timeouts and retries is crucial for agents. Tool calls may fail or become unresponsive, and without timeouts, an agent could remain stuck indefinitely on a tool call. Properly implementing retries and timeouts can be challenging. Even agents with these mechanisms may encounter issues, such as getting stuck when a tool prompts for input on the command line and the agent fails to handle or terminate it. Similarly, an agent might fail to recover from a stalled HTTP request. These scenarios highlight the importance of robust error handling and recovery strategies.

The way agents implement tool usage can significantly impact their performance, even when using the same model.

This underscores why not every agent is suited to operate in full permission mode. Proper safeguards must be in place to prevent misuse or unintended consequences.

