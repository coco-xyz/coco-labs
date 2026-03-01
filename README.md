# COCO Labs

Open-source tools and infrastructure for human-agent collaboration.

**Live site:** [labs.coco.xyz](https://labs.coco.xyz/)

## Products

### Zylos Series — Open Source Agent Framework

| Product | Description | Links |
|---------|-------------|-------|
| **Zylos** | Autonomous AI agent framework — persistent memory, multi-channel communication, task scheduling, extensible skills | [Repo](https://github.com/zylos-ai/zylos-core) |
| **Zylos Telegram** | Telegram messaging component — DM, groups, media, access control | [Repo](https://github.com/zylos-ai/zylos-telegram) |
| **Zylos Lark** | Lark & Feishu messaging component — chat, documents, calendars | [Repo](https://github.com/zylos-ai/zylos-lark) |
| **Zylos Browser** | Browser automation component — navigate, screenshot, interact | [Repo](https://github.com/zylos-ai/zylos-browser) |
| **Zylos ImageGen** | AI image generation using Google Gemini | [Repo](https://github.com/zylos-ai/zylos-imagegen) |

### Claw Series — User-Facing Tools

| Product | Description | Links |
|---------|-------------|-------|
| **ClawMark** | Web annotation & feedback tool — highlight, comment, route to GitHub/Lark/Slack/email | [Repo](https://github.com/coco-xyz/clawmark) · [Releases](https://github.com/coco-xyz/clawmark/releases) |
| **ClawFeed** | Smart RSS reader powered by AI — summarize, categorize, stay informed | [Repo](https://github.com/coco-xyz/clawfeed) |

### HxA Infrastructure — Agent Collaboration

| Product | Description | Links |
|---------|-------------|-------|
| **HxA Connect** | Agent-to-agent communication protocol — real-time WebSocket messaging | [Repo](https://github.com/coco-xyz/hxa-connect) |
| **HxA Teams** | Team organization templates — roles, workflows, human-agent patterns | [Repo](https://github.com/coco-xyz/hxa-teams) |

## Agent-Friendly

This site is designed for both human and AI agent consumption:

- **[llms.txt](https://labs.coco.xyz/llms.txt)** — Machine-readable site description
- **JSON-LD** — Structured data on every page (Schema.org)
- **[ai-plugin.json](https://labs.coco.xyz/.well-known/ai-plugin.json)** — Agent discovery metadata

## Tech Stack

- [Hugo](https://gohugo.io/) static site generator
- [Blowfish](https://blowfish.page/) theme with custom COCO color scheme
- GitHub Pages hosting
- Multilingual: English + 中文

## Local Development

```bash
git clone https://github.com/coco-xyz/coco-labs.git
cd coco-labs
git submodule update --init
hugo server
```

## License

MIT
