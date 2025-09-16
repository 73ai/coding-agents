# State of software engineering with AI 

There has been an explosion of AI coding tools in recent months. We have new models coming out every week, and new tools being built on top of these models.

The common term for these tools is "agents". Coding agents are orchestrators that combine LLMs with various tools and APIs to perform complex coding tasks autonomously or semi-autonomously.

These agents with the power of advanced reasoning models are capable of understanding and generating code, run them and fix errors. As models continues to advance, we can expect even more sophisticated coding agents to emerge, further transforming the software development landscape.

There are 4 major components to the coding agents:

1. Foundation model
2. Agentic loop
3. Tools
4. System prompt

## 1. Foundation Model
The foundation model is the core of the coding agent, providing the overall intelligence and reasoning capabilities.

These models are trained on vast amounts of code, tools and natural language data, enabling them to comprehend programming concepts, syntax, and semantics.

Agents pass the context to the model, which then generates responses based on its understanding of the task at hand.

An agent can use a different types of models, depending on the complexity and requirements of the specific task and capabilities needed for the task.

The deciding factors for choosing a model include:
1. Ability to follow instructions
2. How good the model is at tool use
3. Latency
4. Cost

## 2. Agentic Loop
The agentic loop is the process by which the coding agent performs tasks and learns from its experiences. It is a continuous action and feedback loop that interacts with the environment and solves the tasks at hand.

This loop typically involves the following steps:

1. **Cognition**: The agent collects the context of the current state of the environment, including existing files, previous messages and any user inputs for the current task and sends it to the model.
2. **Action**: Based on the response from the model, the agent determines an action/s, and calls these actions/tools in the environment, such as read or writing files, executing commands, or any other custom tool provided.
3. **Feedback**: The agent sends the results of its actions, such as the output of executed code or the success/failure of a task, back to the model.
4. **Repeat**: This process is repeated iteratively, until the agent achieves its goal or model does not return any more actions.

This iterative process enables coding agents to solve tasks better, as they learn from their successes and failures and adapt their strategies accordingly.

Some things to note about the agentic loop:
- Human in the loop: Incorporating human feedback and oversight can help guide the agent's learning process and improve its performance. So there should be a way to provide feedback to the agent, such as approving or rejecting its actions or interrupting the loop when necessary.
- Timeouts on actions: Implementing timeouts for actions can prevent the agent from getting stuck if it takes too long to run an action and encourage it to explore alternative solutions.

## 3. Tools
Tool use is a critical aspect of coding agents, as it allows them to interact with their environment and perform various tasks that go beyond text generation. Tools can be anything from simple tools like `read_file` and `write_file` to more complex ones like running `shell_commands`, `web_search`.

Agent developers also define custom tools that are specific to their use case, such as `run_tests`, `deploy_code`, or `generate_documentation`.

Model performs better on primitive tools than custom tools, as it has been trained on a wide range of basic operations that are commonly used in programming tasks. 

For ex. instead of having a custom tool to run tests, you can use a primitive tool like `run_shell_command` to execute the test command directly in the shell and figure out the command by reading the readme file.


## 4. System Prompt
The system prompt is a crucial component of coding agents, as it defines the agent's behavior, capabilities, and constraints. A well-designed system prompt can significantly enhance the agent's performance and ensure it operates within the desired parameters. Key aspects of a system prompt include:
- **Role definition**: Clearly defining the agent's role and responsibilities, such as being a coding assistant, a code reviewer, or a debugging tool
- **Capabilities**: Specifying the agent's capabilities, such as understanding specific programming languages, frameworks, or tools
- **Constraints**: Outlining any limitations or restrictions on the agent's actions, such as not modifying certain files or adhering to specific coding standards
- **Context**: Providing relevant context or background information that can help the agent make informed decisions and generate appropriate responses


# Types of Coding Agents

There are roughly five main types of coding agents currently in use:

1. IDE Extensions
2. Web Based Agents
3. General-purpose CLI Agents
4. Use case specific Bots
5. Autonomous Agents
6. Background Task Agents

There's no single tool to recommend because the landscape is so fragmented and a tool that works for one person might not work for another. The best approach is to understand how they function and what trade-offs they make.

## Perpetual Prototypes

One of the most significant benefits of coding agents is their ability to create **"perpetual prototypes."** Imagine being in the middle of a project and wishing you had a small, temporary debugging tool or a better way to visualize data. With a coding agent, you can create these small, purpose-built tools on the fly. This makes the development workflow more enjoyable and efficient, as you can have the agent on the side working on these helpful utilities.

For this to work well, you need a tool that allows for a mix of "hands-on" and "hands-off" interaction. This is different from a fully detached tool like a GitHub extension that makes a change in a pull request, where it's much harder to understand the impact of your changes. CLI-based or IDE-integrated tools are great for this because they allow for quick experimentation and steering the agent as it works.

# State of existing coding tools/agents

There are several tools available today, each with its own strengths and weaknesses. Some of the most notable ones include:


## 1. IDE Extensions (Editor Based Tools)

Tools like **GitHub Copilot** and **Cursor** are the most well-known IDE extensions. They act as autocomplete but can also perform more complex coding loops. Editor based tools like Github Copilot, Cursor, WindSurf, Tabnine, Cline, Kilo Code etc. are integrated into code editors (like VSCode) and provide real-time code suggestions and completions based on the context of the current file and the history.

Cursor, for example, has become very capable and can even run on a remote server. Recently most of these tools have this new mode ("Agent Mode") that allows users to use it with agent loop, where the agent can perform complex coding tasks with human in the loop.

## 2. Web Based Tools

Web based tools like Replit, v0, Lovable, Firebase Studio, etc. provide a web-based coding environment with agent capabilities. These are often very similar to other coding agents in how they work, but they are specifically targeted at creating user interfaces. They behave differently from a general-purpose tool, as they are geared toward a single goal - allowing users to build web applications directly in the browser by providing a set of instructions. 

Most of these tools are primarily focused on UI/frontend oriented web development, but some also support for serverless storage engines like Firebase, Supabase allowing users to build full-stack applications without needing to set up a local development environment.

They also include deployment capabilities, allowing users to deploy their applications directly from the same environment.


## 3. General-purpose CLI Tools (Terminal Based)

CLI based tools like Claude Code, OpenAI Codex, Gemini CLI, Cursor CLI, OpenCode etc. are terminal based tools that provide a terminal user interface for interacting with the AI coding agent, allowing users to perform various tasks through text input. These general-purpose, local tools run on your local machine and can access anything you give them permissions for, making them very versatile.

These tools can do pretty much everything on your local machine given the right permissions, such as reading and writing files, executing commands, and even deploying code.

Claude code is the first tool in this category and became most popular tool among developers since launch, as it provides a powerful model that is good at following instructions and tool use, with the reasonable usage limit on their fixed cost subscription plans.

Claude Code, OpenAI Codex and Gemini CLI are the tool by Anthropic, OpenAI and Google respectively. They restrict the usage of their models to their own tools, which means you cannot use any other model with these tools.

## 4. Use case specific Bots
1. Bots are use case specific agents that are designed to perform specific tasks or workflows, such as code review, bug fixing, or documentation generation. 

Example of bots including Code Rabbit, etc.


## 5. Autonomous Agents

These standalone agents can work independently, often through a CLI or running on a remote server. Tools like **Devin** fall into this category. They can perform agent loops on given tasks autonomously. 

Github Copilot, Claude Code etc. provide this capability, where the users can assign a github issue to the tool and it will churn out the PR by performing the agent loop on the issue description and any other relevant context given in the issue.

Cursor recently released server version of their tool, which allows users to perform tasks remotely.

## 6. Background Task Agents
TBD

## Factors to consider when choosing a coding agent
When choosing a coding agent, there are several factors to consider:
1. **Model capabilities**: The foundation model's ability to understand and generate code, follow instructions, and use tools effectively.
2. **Tool availability**: The range of tools and APIs that the agent can access, as well as the ease of integrating custom tools.
3. **User experience**: The overall user experience, including the interface, ease of use, and responsiveness of the agent.
4. **Cost**: The pricing model of the agent, including any usage limits, subscription plans, or pay-as-you-go options.
5. **Community and support**: The availability of community resources, documentation, and support channels to help users get the most out of the agent.

