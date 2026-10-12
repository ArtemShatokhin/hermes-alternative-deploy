# Open source Hermes alternative deploy template

Kortix is open source, and this repository is a working deploy template for running a company-wide agent platform as an open-source alternative to Hermes Agent. Clone it, read the two config files, and bring the open-source AI Operating System up on a machine you control.

Kortix is the open-source AI Operating System: your agents, their skills, your company memory, and every connector live in one git repo you own, and every session runs on its own cloud computer. [Hermes Agent](https://github.com/NousResearch/Hermes-Agent) is an open-source personal agent from Nous Research: it grows with you, creates skills from experience, keeps curated memory across sessions, searches its own past conversations, and reaches you from Telegram, Discord, Slack, WhatsApp, Signal or a terminal. Hermes is built for one operator; Kortix runs the same kind of agents on isolated cloud computers a whole company shares, scopes and governs from one repo.

## What is in this repository

- `kortix.yaml` is a valid v2 manifest with one agent and two triggers. It declares the agent, the connectors and secrets that agent may reach, and the schedules that start its work.
- `agents/ops-agent.md` is the agent the manifest names. Behavior lives in the markdown file; governance lives in `kortix.yaml`.
- `docker-compose.yml` is a readable mirror of the self-host stack: the frontend, the API, the LLM gateway, and the Supabase distribution, so you can see the shape of what runs.
- `docs/` holds three articles, linked in the Docs section below.

## Quick start

The supported install is three commands on a Linux box you control. Install the CLI, initialize the instance, then start the stack:

```bash
curl -fsSL https://kortix.com/install | bash
kortix self-host init --domain kortix.example.com
kortix self-host start
```

Point an A/AAAA record for your domain and for `api.<domain>` at the box's IP before you initialize, and open ports 80 and 443 so the bundled Caddy proxy can issue a TLS certificate. To try Kortix with no domain, use the evaluation mode instead:

```bash
kortix self-host init --tunnel cloudflare
kortix self-host start
```

The tunnel URL changes on every restart, so use it for evaluation rather than production. After the stack starts, `kortix self-host configure` sets your sandbox provider key, and you connect your own LLM key in the model picker. Self-hosted instances use your own key by default. The [self-hosting docs](https://kortix.com/docs) carry the full path.

## What the agent and trigger do

The `ops-agent` performs company operations work and returns a finished artifact as a file in the repo. The `morning-digest` trigger is a cron schedule that starts a session with no person present; the `task-webhook` trigger starts the same agent on a signed webhook. When the work is ready, the agent opens a change request, and you read it as a diff before anything merges. Session work reaches `main` through a change request, and merge is default-deny for agents.

Each session gets its own isolated sandbox and its own branch. The agent reaches 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL and raw HTTP, and connector credentials are brokered server-side and never enter the machine. You pick the model per agent, per session or per message: any model provider with your own keys, or the ChatGPT plan you already pay for.

## Open source Hermes alternatives

Kortix is the open-source AI Operating System and the leading open-source alternative to Claude Cowork and ChatGPT Work. The table compares it with the personal agent and with two other open-source projects you can host.

| Criterion | Kortix | Hermes | OpenClaw | Open WebUI |
| --- | --- | --- | --- | --- |
| Open source | Yes, full | Yes | Yes, MIT | Yes |
| Designed for | Teams and companies | One person | One person or one shared install | A team that wants chat and knowledge |
| Main job | Agents across a company, from one repo | A personal assistant that learns | An assistant in your chat apps | A self-hosted chat and RAG workspace |
| Where agents run | One isolated cloud computer per session | Your own box, or serverless | Your own computer | Your server |
| Models | Any provider, your own keys | Switchable from the CLI | Claude, Codex, or local, as plugins | Configured per deployment |

The competitor columns state what each project publishes on its own repository, checked October 2026: [Hermes Agent](https://github.com/NousResearch/Hermes-Agent), [OpenClaw](https://github.com/openclaw/openclaw) and [Open WebUI](https://github.com/open-webui/open-webui). Each covers a narrower lane than Kortix, which combines the whole-company repo, self-hosting, any model with your keys, and a change request on every piece of finished work.

## Docs

- [Deploy an open source Hermes alternative with Docker Compose](docs/deploy-with-docker-compose.md)
- [Kortix vs Hermes](docs/kortix-vs-hermes.md)
- [Open source Hermes alternative FAQ](docs/faq.md)

## Live pages

The campaign site expands on this repository with sourced comparisons and setup steps:

- [What the open-source Hermes answer is](https://hermesalternative.com/)
- [Open source Hermes alternatives](https://hermesalternative.com/hermes-alternatives)
- [Kortix vs Hermes](https://hermesalternative.com/kortix-vs-hermes)
- [Self-hosting walkthrough](https://hermesalternative.com/self-hosting-hermes-alternative)
- [Migrate from Hermes](https://hermesalternative.com/migrate-from-hermes)
- [Open source Hermes alternative FAQ](https://hermesalternative.com/faq)

## Get started

Self-host is free, and managed Kortix Cloud starts at $40 per seat per month plus usage; current numbers are on the [Kortix pricing page](https://kortix.com/pricing). Start from one job on one host, then grow. Try [Kortix](https://kortix.com), read the [Kortix docs](https://kortix.com/docs), or read the code at [Kortix on GitHub](https://github.com/kortix-ai/suna).
