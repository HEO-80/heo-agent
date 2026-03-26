<div align="center">

<br/>

# ⚡ HEO-AGENT

### Building a personal AI ecosystem — documented in public.

A long-term project to design, build, and document a fully autonomous  
personal AI infrastructure: agents, automation, tools, and memory.  
From a Mini PC running 24/7 to multi-agent architectures and DeFi automation.

<br/>

[![Status](https://img.shields.io/badge/Status-In_Progress-f7df1e?style=for-the-badge)](https://github.com/HEO-80/heo-agent)
[![Phase](https://img.shields.io/badge/Phase-1_of_4-82aaff?style=for-the-badge)](https://github.com/HEO-80/heo-agent)
[![Built by](https://img.shields.io/badge/Built_by-HEO--80-ff4d4d?style=for-the-badge&logo=github&logoColor=white)](https://github.com/HEO-80)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-hectorob-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/hectorob)

<br/>

</div>

---

<div align="center">

## 🧭 What is this?

</div>

HEO-AGENT is not a single app. It's a **personal AI infrastructure project** built incrementally and documented publicly — every decision, every mistake, every working setup.

The goal: a system where AI agents handle real tasks across projects, communication channels, automation flows, and eventually DeFi/Web3 operations — running mostly free, mostly local, always on.

This repo is the **central hub**: roadmap, architecture decisions, tool comparisons, and links to every sub-project.

---

<div align="center">

## 🗂️ Project Map

</div>

| Repo | Description | Status |
|---|---|---|
| [beelink-ai-server](https://github.com/HEO-80/beelink-ai-server) | 24/7 AI server on Mini PC — OpenClaw + Telegram + Gemini | ✅ Phase 1 done |
| [CodeTyper](https://github.com/HEO-80/CodeTyper) | Typing trainer for developers with live semantic highlighting | 🔧 Active |
| [netwatch-terminal](https://github.com/HEO-80/netwatch-terminal) | Cyberpunk desktop terminal — Tauri + React + Rust | ✅ Done |
| [vaultflow](https://github.com/HEO-80/vaultflow) | Web3 smart contract escrow platform | 🔧 In progress |
| heo-agent *(this repo)* | Project hub — roadmap, architecture, docs | 📖 Living doc |

---

<div align="center">

## 🏗️ Target Architecture

</div>

```
📱 Telegram / WhatsApp
        ↕
🖥️  Beelink (always-on server)
    ├── OpenClaw Gateway  ←→  Gemini / Claude API
    ├── n8n (automation flows)
    └── Agent Memory + Skills
        ↕
🖥️  Main PC (when online)
    └── Ollama (local models — RX 9070 XT · 16GB VRAM)
        ↕
🔗  Web3 / DeFi Layer
    └── VaultFlow · VLBots · BSC / ETH Mainnet
```

---

<div align="center">

## 📅 Phases

</div>

### ✅ Phase 1 — Foundation (done)
- Mini PC server running 24/7 on Ubuntu
- OpenClaw gateway as systemd service
- Telegram bot connected to Gemini 2.5 Flash (free OAuth)
- Monitoring stack: Grafana + Prometheus
- → [beelink-ai-server](https://github.com/HEO-80/beelink-ai-server)

### 🔧 Phase 2 — Skills & Automation (next)
- Enable OpenClaw skills: `notion`, `github`, `weather`, `summarize`
- Telegram pairing (owner-only access)
- n8n integration for automated flows
- Agent memory across sessions

### ⏳ Phase 3 — Local Models
- Ollama on main PC (RX 9070 XT, 16GB VRAM)
- Hybrid routing: cloud API when server is off, local model when PC is on
- Model comparison: Gemini Flash vs local Qwen / Llama

### ⏳ Phase 4 — Multi-Agent & Web3
- Multiple specialized agents (projects, ideas, teaching, DeFi)
- VaultFlow integration
- VLBots DeFi automation layer

---

<div align="center">

## 🔬 Tool Comparisons

</div>

| Tool | Type | Use case | Verdict |
|---|---|---|---|
| OpenClaw | Agent framework | Always-on personal assistant via messaging | ✅ Production setup |
| n8n | Automation orchestrator | Predefined flows, integrations | Planned Phase 2 |
| Ollama | Local LLM runner | Private / offline inference | Planned Phase 3 |
| Zapier / Make | No-code automation | Quick integrations | Not in stack |

> Detailed comparisons and decisions are documented in [`/docs`](./docs).

---

<div align="center">

## 💡 Philosophy

</div>

- **Build in public** — every phase is documented, including what broke
- **Free first** — explore free tiers before paying anything
- **Own your stack** — prefer self-hosted over SaaS where practical
- **Real use cases** — no toy demos, everything built for actual daily use
- **Cross-domain** — developer tooling, teaching, DeFi, and automation in the same ecosystem

---

<div align="center">

## 📄 License

MIT — see [LICENSE](LICENSE) for details.

---

<br/>

Built by [HEO-80](https://github.com/HEO-80) · [LinkedIn](https://linkedin.com/in/hectorob) · Zaragoza, Spain

<br/>

</div>
