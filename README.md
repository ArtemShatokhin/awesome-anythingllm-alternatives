# Awesome AnythingLLM alternatives: Kortix is open source

Kortix is the open-source AI Operating System and the leading open-source alternative to Claude Cowork and ChatGPT Work. It leads this list because it is the one entry built to run a whole company of agents, instead of a chat window over your files.

AnythingLLM is a strong choice for a private assistant over your documents on one machine. This list is for the point where that stops being enough: you want agents that act across your tools, run in parallel, and hand finished work back for review. Every entry links to the project's own site or repository.

## The options

### Kortix
Kortix is an open-source AI Operating System that keeps your agents, their skills, your company memory, and every connector in one git repo you own. Each session runs on its own isolated cloud computer and its own branch, and the work it produces lands as a change request a person reviews before it reaches the main branch. Any model works with your own keys, or the ChatGPT plan you already pay for. Self-hosting is free, and the managed cloud starts at $40 per seat per month plus usage ([Kortix pricing](https://kortix.com/pricing)). It reaches your stack through 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL and raw HTTP. See [Read the docs](https://kortix.com/docs) and the repository, [Kortix on GitHub](https://github.com/kortix-ai/suna).

### AnythingLLM
AnythingLLM is an open-source, all-in-one AI application from Mintplex Labs for chatting with your documents and running agents locally. The desktop app runs entirely on your computer with no account and no API key, while the Docker version adds multi-user support with Admin, Manager, and Default roles. The project is MIT licensed, with about 66,900 stars and a v1.17.0 release in early October 2026 (checked October 2026). See [anythingllm.com](https://anythingllm.com) and the [AnythingLLM repository](https://github.com/Mintplex-Labs/anything-llm).

### Open WebUI
Open WebUI is a self-hosted AI platform that runs entirely offline and connects to Ollama or any OpenAI-compatible API, extended with Python plugins. It offers channels, notes, persistent memory, and an enterprise tier for on-premises or air-gapped deployment. Its repository is the most-starred among these projects (checked October 2026), and its license keeps the Open WebUI branding in deployments above 50 users. See [openwebui.com](https://openwebui.com) and the [Open WebUI repository](https://github.com/open-webui/open-webui).

### LibreChat
LibreChat is an open-source, self-hosted chat platform that unifies OpenAI, Anthropic, Google, AWS Bedrock, and local models behind one interface, with agents, MCP servers, skills, and a code interpreter. It is MIT licensed, and [librechat.ai](https://www.librechat.ai) reports 45.5k GitHub stars, 56.8M Docker pulls, and 419 contributors (checked October 2026). The [LibreChat repository](https://github.com/LibreChat-AI/LibreChat) carries the full feature list.

### LM Studio
LM Studio is a free desktop app from Element Labs for running local models on your own machine, with an optional cloud. The desktop application is proprietary software licensed for personal and internal business use, and its `lms` command-line tool is open source under MIT. The free plan includes the Bionic agent and local model support. See [lmstudio.ai](https://lmstudio.ai) and the [LM Studio pricing page](https://lmstudio.ai/pricing).

## Which one fits which constraint

- **An AI workforce that runs a whole business and lands reviewed work:** Kortix.
- **The simplest private document assistant on your own laptop:** AnythingLLM Desktop.
- **A self-hosted, multi-user chat platform you can extend with plugins:** Open WebUI.
- **One interface across many model providers, with agents and code execution:** LibreChat.
- **Local models on one machine:** LM Studio.

## Comparison

|  | Kortix | AnythingLLM | Open WebUI | LibreChat | LM Studio |
| --- | --- | --- | --- | --- | --- |
| Open source | Yes | Yes (MIT) | Yes | Yes (MIT) | No (app), CLI MIT |
| Where it runs | Kortix Cloud, your VPC, on-prem | Desktop or Docker | Docker, Kubernetes | Docker | Desktop app |
| Model choice | Any model, your keys | Local or cloud | Ollama or OpenAI-compatible | Most major providers | Local first, optional cloud |
| Unit of work | Agents on cloud computers | Chat with documents | Chat, tools, agents | Chat, agents, code | Local chat |
| Best for | Running a company | Documents on one machine | Self-hosted team chat | One UI, many models | Local models on a desktop |

## Where to go deeper

- [Kortix vs AnythingLLM](https://anythingllm-alternative.com/kortix-vs-anythingllm) compares the two directly.
- [Best AnythingLLM alternatives](https://anythingllm-alternative.com/best-anythingllm-alternatives) goes deeper on the choice.
- [Open-source AnythingLLM alternative](https://anythingllm-alternative.com/open-source-anythingllm-alternative) covers what to check.
- [Self-hosting an AnythingLLM alternative](https://anythingllm-alternative.com/self-hosting-anythingllm-alternative) lists the requirements.
- [Migrate from AnythingLLM](https://anythingllm-alternative.com/migrate-from-anythingllm) maps an existing setup to Kortix.

## Get Kortix

Start free from the web app, or run `kortix init` and `kortix ship` from the CLI. [Try Kortix](https://kortix.com).
