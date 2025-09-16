# Tool Safety and Hidden Hurdles

Beyond the choice of model and tools, there are other factors that significantly impact an agent's performance and safety.

## Pre-flights and Post-flights

Some of the best agents add extra steps to each loop. For example, a "pre-flight" check might use a smaller, faster LLM to double-check the user's prompt, while a "post-flight" check might verify that a tool command is safe to run.

Claude Code, for instance, uses the fast Haiku model to assess whether a proposed tool command is safe to execute. This extra layer of security helps prevent the agent from deleting the wrong files or doing something else destructive. Not all agents have these safeguards, which means some are not safe to run in a "yolo mode" (with full permissions).

## Error Handling

Even with the best tools, things can go wrong. A good agent needs to know what to do if a command fails, a web request gets stuck, or a program doesn't compile. A poorly built agent might just get stuck and never recover, wasting time and resources. This is a key difference between battle-tested tools and newer ones.

Implementing timeouts and retries is crucial for agents. Tool calls may fail or become unresponsive, and without timeouts, an agent could remain stuck indefinitely on a tool call. Even agents with these mechanisms may encounter issues, such as:
- Getting stuck when a tool prompts for input on the command line and the agent fails to handle or terminate it
- Failing to recover from a stalled HTTP request
- Running into infinite loops when error messages aren't properly parsed

These scenarios highlight the importance of robust error handling and recovery strategies. Some agents are "battle-tested" for autonomous use for extended periods, while others haven't been thoroughly tested for edge cases.

## Parallelization

Some agents are capable of running multiple tasks at once, which can improve speed. However, this is not always possible and depends on the specific task. Parallelization requires careful coordination to avoid conflicts and ensure that parallel operations don't interfere with each other.

## Why This Matters

The way agents implement tool usage can significantly impact their performance, even when using the same model. These nuances make it incredibly difficult to evaluate and compare agents. Public benchmarks can give you some numbers, but they don't capture the full picture of safety, reliability, and real-world performance.

This underscores why not every agent is suited to operate in full permission mode. Proper safeguards must be in place to prevent misuse or unintended consequences.

