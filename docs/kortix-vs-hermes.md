# Kortix vs Hermes

Both Kortix and Hermes are open source. They are built around different units: Hermes Agent is a personal agent that grows with one operator, and Kortix is a platform a whole company runs and governs from one repository.

## The head-to-head

| Dimension | Kortix | Hermes |
| --- | --- | --- |
| What it is | The open-source AI Operating System | An open-source personal AI agent |
| Designed for | Teams and companies | One operator |
| Where agents run | One isolated cloud computer per session, on its own branch | Your own box, a GPU cluster, or serverless |
| Memory | Files in a memory directory inside the repo you own | Curated memory it keeps across sessions |
| Reach | Web, Slack, Microsoft Teams, CLI, API and mobile | Telegram, Discord, Slack, WhatsApp, Signal or a terminal |
| Governance | Per-resource permissions for people and agents; approval gates; an audit trail | What one operator configures |
| Models | Any provider with your own keys, or the ChatGPT plan you already pay for | Switched from the CLI |
| Finished work | Opens a change request; merge is default-deny for agents | Runs as the operator's assistant |

Hermes's rows come from its own repository, [github.com/NousResearch/Hermes-Agent](https://github.com/NousResearch/Hermes-Agent), checked October 2026: it describes an agent that creates skills from experience, keeps curated memory, searches its own past conversations, and runs on a $5 VPS or serverless. Kortix's rows come from the [Kortix docs](https://kortix.com/docs).

## When Hermes is the right fit

Pick Hermes when one person wants an always-on personal agent on their own machine that learns from their work. That is what a personal agent is for.

## When Kortix is the right fit

Pick Kortix when the agents are shared. One git repo holds every agent, skill, memory file and connector. Per-resource permissions decide what a person or an agent may touch, approval gates can hold a tool call, and finished work lands through a change request a person reads as a diff. Self-host it free, run it in your VPC, or use Kortix Cloud.

## The short decision

One operator, one agent, own machine: Hermes. A team that needs shared, governed agents on infrastructure it controls: Kortix.
