# COCO Labs

Open-source tools and infrastructure for human-agent collaboration.

**Live site:** [labs.coco.xyz](https://labs.coco.xyz/)

## Products

### Claw Series — User-Facing Tools

| Product | Description | Links |
|---------|-------------|-------|
| **ClawMark** | Web annotation & feedback tool — highlight, comment, and route to GitHub/Lark/Slack/email | [Repo](https://github.com/coco-xyz/clawmark) · [Releases](https://github.com/coco-xyz/clawmark/releases) |
| **ClawFeed** | Smart RSS reader powered by AI — summarize, categorize, stay informed | [Repo](https://github.com/coco-xyz/clawfeed) |
| **ClawFi** | AI-powered family finance manager — expenses, budgets, financial insights | [Repo](https://github.com/hxa-k/clawfi) |

### HxA Infrastructure — Agent Collaboration

| Product | Description | Links |
|---------|-------------|-------|
| **HxA Connect** | Agent-to-agent communication protocol — real-time WebSocket messaging | [Repo](https://github.com/coco-xyz/hxa-connect) |
| **HxA Teams** | Team organization templates — roles, workflows, human-agent patterns | [Repo](https://github.com/coco-xyz/hxa-teams) |
| **HxA Workspace** | Collaboration platform — identity, knowledge, dashboards, meetings | [Repo](https://github.com/coco-xyz/hxa-workspace) |

## Tech Stack

- **[Hugo](https://gohugo.io/)** static site generator
- **[Blowfish](https://blowfish.page/)** theme with custom COCO color scheme
- **GitHub Pages** hosting
- Custom CSS: amber/gold accent (#F59E0B) + Plus Jakarta Sans font

## Local Development

```bash
git clone https://github.com/coco-xyz/coco-labs.git
cd coco-labs
git submodule update --init
hugo server
```

Open [localhost:1313](http://localhost:1313) to preview.

## License

MIT
