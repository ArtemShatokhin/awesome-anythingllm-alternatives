# How to self-host an AnythingLLM alternative

Self-hosting an AnythingLLM alternative is possible for almost every option here, and most of them cost nothing beyond the machine you run them on. The trade is control for upkeep: you own the data and the configuration, and you also own updates, backups, and the box itself. What each platform needs to run on your own hardware varies mostly by how many people share it.

AnythingLLM is itself open source and self-hostable, so the real question is which alternative to move to and how much of the setup you want to manage.

## What self-hosting means here

Self-hosting means the application and its data run on a server you control, usually a machine in your office, a cloud VM, or a VPC. Your documents, embeddings, and user accounts stay on that machine. You reach it through a browser on your network or the internet. You are responsible for the operating system, the storage, the TLS certificate, and the upgrade path.

For a single user who only wants local model inference, self-hosting is often unnecessary, because desktop apps such as AnythingLLM Desktop and LM Studio already run everything on the laptop. The distinction matters once several people need one shared instance.

## Self-hosting AnythingLLM

AnythingLLM ships a Docker edition built for servers. The Docker version is both single-user and multi-user, with three roles (Admin, Manager, and Default), embeddable chat widgets, white-labeling, and browser access. The desktop app is single-user, has a built-in LLM provider, and keeps everything on the device. Both are open source, and the Docker path can run locally or on cloud services such as AWS, Google Cloud, or Railway ([installation overview](https://docs.anythingllm.com/installation-docker/overview)).

The catch is that multi-user mode in AnythingLLM is a one-way configuration change, so decide before you enable it. If you would rather not run the server at all, AnythingLLM's own managed cloud starts at $50 per month for a Basic private instance and $99 per month for Pro ([AnythingLLM Cloud](https://anythingllm.com/cloud)).

## Self-hosting Open WebUI

Open WebUI is a self-hosted AI platform that runs entirely offline and connects to Ollama or any OpenAI-compatible API. The fastest install is a single Docker command:

```bash
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway \
  -v open-webui:/app/backend/data \
  -e WEBUI_SECRET_KEY=your-secret-key \
  --name open-webui --restart always \
  ghcr.io/open-webui/open-webui:main
```

Then open `http://localhost:3000`. The `:main` image carries the embedding, speech, and reranking models, so retrieval and voice work on first start; the `:slim` tag is 196 MB instead of 1.62 GB when your models run through a hosted API or a separate Ollama server. Open WebUI also installs through pip, uv, Kubernetes, or a desktop app, and it offers an enterprise tier for on-premises or air-gapped deployment ([Open WebUI docs](https://docs.openwebui.com)).

## Self-hosting LibreChat

LibreChat is an open-source, self-hosted chat platform that fronts OpenAI, Anthropic, Google, AWS Bedrock, and local models through one interface. It is MIT licensed and ships a bundled Docker Compose stack for a one-command setup, with a browser admin panel for users, groups, roles, and per-role permissions that you can edit without redeploying ([LibreChat repository](https://github.com/LibreChat-AI/LibreChat)). It scales from a single server to a horizontally scaled deployment with Redis.

## Self-hosting Kortix

Kortix is an open-source AI Operating System, and self-hosting is free. The CLI brings up your own instance as one Docker Compose stack, or you can run Kortix Cloud or place it in your own VPC or on your own on-prem network. The first run asks six things and no model key; GitHub connects in the dashboard and models are bring-your-own-key in the app.

```bash
curl -fsSL https://kortix.com/install | bash
kortix self-host start
```

Inside a Kortix instance, your agents, skills, company memory, and connectors live in one git repo you own, and each session runs on its own isolated cloud computer and its own branch. Work reaches the main branch only through a change request a person reviews. The instance must be reachable so a session's machine can call back to it, and the quick start pulls images from docker.io ([Kortix docs](https://kortix.com/docs), [Kortix on GitHub](https://github.com/kortix-ai/suna)).

## Choosing a self-host path

|  | Kortix | AnythingLLM | Open WebUI | LibreChat |
| --- | --- | --- | --- | --- |
| Open source | Yes | Yes (MIT) | Yes | Yes (MIT) |
| First step | `kortix self-host start` | Docker image | One Docker command | Docker Compose |
| Multi-user | Roles, groups, permissions | Docker only | RBAC and groups | Role-based admin |
| Team isolation | A sandbox per session | Shared workspaces | Shared instance | Shared instance |

The practical difference is what runs per task. AnythingLLM, Open WebUI, and LibreChat host people in shared workspaces. Kortix runs each session on its own isolated sandbox, so parallel work does not collide and every change lands through review.

If you are moving an existing setup, the [self-hosting AnythingLLM alternative guide](https://anythingllm-alternative.com/self-hosting-anythingllm-alternative) maps the options, and [Migrate from AnythingLLM](https://anythingllm-alternative.com/migrate-from-anythingllm) covers moving your documents and workspaces across.
