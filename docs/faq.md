# Open source Hermes alternative FAQ

## Is Kortix open source?

Yes. Kortix is the open-source AI Operating System. The code is public: read it, fork it and audit it at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Is Hermes Agent open source?

Yes. Hermes Agent is an open-source personal agent from Nous Research ([NousResearch/Hermes-Agent](https://github.com/NousResearch/Hermes-Agent), checked October 2026).

## What is the difference between Kortix and Hermes?

Hermes is a personal agent built for one operator: it learns from their work and reaches them in their chat apps. Kortix is a platform a whole company runs from one git repo, where agents share memory and connectors, each session is isolated, and finished work lands through a change request a person approves.

## Can I self-host Kortix for free?

Yes. Self-host is free, and the stack is one Docker Compose project. You pay only for the compute you point it at and the model keys you bring.

## Which models can Kortix run?

Any model provider with your own keys, or the ChatGPT plan you already pay for. You pick the model per agent, per session or per message.

## Where does Kortix run?

Kortix Cloud, your own VPC, or your own on-prem network. Self-hosted instances run the control plane on your hardware, and agent sessions run on a separate sandbox provider.

## Where do people use Kortix?

Kortix runs in the web app, in Slack and Microsoft Teams, from the CLI, over the API and on mobile. A message in a channel starts a session whose agent replies in the same thread.

## How does the work get approved?

Session work reaches `main` through a change request you read as a diff before anything merges. Merge is default-deny for agents, and approval gates can hold any tool call until a person approves it.
