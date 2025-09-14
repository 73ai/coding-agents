# System Prompt

Creating the Prompt
● Collect context
● Rank context
● Trim context
● Assembling Prompt


In context of Github copilot
Creating the Prompt: Copilot Code Completion● Collect context – current document, open tabs, symbols, file path
● Rank context – file path → current document → open tabs → symbols
● Trim context – drop open tab snippets; truncate current document
● Assembling Prompt


Creating the Prompt: Copilot Chat
● Collect context:
○ References – files, snippets, issues, that users attach or tools produce
○ Prior messages
● Rank, Trim and Assemble:
○ must fit:
■ system message
■ function definitions (if we plan to use them)
■ user's most recent message
○ fit if possible:
■ all the function calls and evals that follow
■ the references that belong to each message
■ historic messages (most recent being most important)
○ fallback to no-function usage if we can't fit with (causes Assistant to respond and turn to
complete)

Tips for Defining Tools
● Don't have "too many" tools - look for evidence of collisions
● Name tools simply and clearly (and in typeScript format?)
● Don't copy/paste your API - keep arguments simple and few
● Keep function and arg descriptions short and consider what the model
knows
○ It probably understands public documentation.
○ It doesn't know about internal company acronyms.
● More on arguments
○ Nest arguments don't retain descriptions
○ You can use enum and default, but not minimum, maximum…
● Skill output – don't include extra "just-in-case" content
● Skill errors – when reasonable, send errors to model (validation errors)