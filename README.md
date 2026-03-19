# ring-ai

Ring-specific AI tools (skills, plugins, agents) for developers and AI agents integrating the Ring ecosystem.

## Quick Start

```bash
# Skills CLI (any agent)
npx skills add ringprotocol/ring-ai

# Claude Code Marketplace
/plugin marketplace add ringprotocol/ring-ai

# Install individual plugins
/plugin install ring-trading       # Swap integration
/plugin install ring-driver        # Swap & liquidity planning
/plugin install ring-to-wallet     # Install dapp to wallet
```

## Featured Skills

| Skill                | Plugin       | Description                                                     |
| -------------------- | ------------ | --------------------------------------------------------------- |
| `swap-integration`   | ring-trading | Integrate Ring swaps via Trading API, Universal Router, or SDKs |
| `pay-with-any-token` | ring-trading | Pay HTTP 402 challenges (MPP/x402) using tokens via Ring swaps  |

## Documentation

| Document                                   | Description                              |
| ------------------------------------------ | ---------------------------------------- |
| [Project Overview](./docs/OVERVIEW.md)     | Plugins, architecture, development setup |
| [Getting Started](./docs/getting-started/) | Installation and quick start guide       |

## Contributing

See [Project Overview](./docs/OVERVIEW.md) for development setup and contribution guidelines.

## License

MIT License - see [LICENSE](./LICENSE) for details.
