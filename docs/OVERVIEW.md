# Ring AI

Ring-specific AI tools (skills, plugins, agents) for developers and AI agents integrating the trading API.

## Overview

This repository provides Claude Code plugins and AI development tools specifically designed for building on the Ring protocol.

## Installation

### Skills CLI (Any Agent)

```bash
# Install all Ring AI skills via the skills.sh CLI
npx skills add ringprotocol/ring-ai
```

### Claude Code Marketplace

````bash
# Install the ring-ai plugin marketplace
/plugin marketplace add ringprotocol/ring-ai

## Plugins


### ring-trading

Integrate Ring swaps via Trading API, Universal Router SDK, or direct smart contract calls.

**Skills:** `swap-integration`

### ring-driver

Plan Ring swaps and liquidity positions with deep link generation for the Ring interface.

**Skills:** `swap-planner`, `liquidity-planner`


## Agent-Agnostic Design

All tools in this repository are designed to work with any LLM coding agent, not just Claude Code:

- **AGENTS.md** symlinks to CLAUDE.md for cross-agent compatibility
- Prompts are written to work across different models
- Skills are structured as markdown that any agent can interpret

## Documentation

- [Getting Started](./getting-started/index.md)
- [Skills Reference](./skills/index.md)
- [Evals Guide](./evals/index.md)

## Development

### Prerequisites

- Node.js 22.x
- npm 11.7.0

### Setup

```bash
# Install dependencies
npm install

# Build all packages
npx nx run-many -t build

# Run tests
npx nx run-many -t test

# Run linting
npx nx run-many -t lint
````

### Project Structure

```text
ring-ai/
├── packages/
│   └── plugins/         # Claude Code plugins (skills live here)
├── evals/               # AI tool evaluations (Promptfoo)
├── docs/                # VitePress documentation
└── scripts/             # Build and validation scripts
```

## Contributing

Contributions are welcome. Please ensure:

1. All code passes linting and tests
2. New skills include eval suites
3. Documentation is updated

### Automated Checks

PRs are automatically validated by several workflows:

- **PR Checks** - Build, lint, test, documentation prose linting, and plugin validation
- **Claude Code Review** - AI-powered code review with inline comments
- **Claude Docs Check** - Validates CLAUDE.md and README updates, ensures plugin version bumps

If the docs check flags missing documentation updates, you can apply the suggested changes directly from the PR comments.

See [.github/workflows/CLAUDE.md](https://github.com/ringprotocol/ring-ai/blob/main/.github/workflows/CLAUDE.md) for detailed CI documentation.

## License

MIT License - see [LICENSE](https://github.com/ringprotocol/ring-ai/blob/main/LICENSE) for details.

## Links

- [Ring API Docs](https://api-docs.ring.exchange/introduction)
- [Ring v4 Docs](https://docs.ring.exchange/contracts/v4/overview)
- [Claude Code](https://claude.ai/code)
