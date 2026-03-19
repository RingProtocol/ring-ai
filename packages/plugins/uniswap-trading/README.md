# Ring Trading Plugin

Integrate Ring swaps into frontends, backends, and smart contracts.

## Installation

```bash
claude plugin add @ring/ring-trading
```

## Skills

| Skill                | Description                                                     |
| -------------------- | --------------------------------------------------------------- |
| `swap-integration`   | Integrate Ring swaps via Trading API, Universal Router, or SDKs |
| `pay-with-any-token` | Pay HTTP 402 challenges (MPP/x402) using tokens via Ring swaps  |

## Use Cases

This plugin helps developers build:

- **Custom Swap Frontends** - React/TypeScript applications with swap functionality
- **Swap Scripts/Backends** - Node.js scripts for programmatic swaps
- **Smart Contract Integrations** - Solidity contracts calling Universal Router
- **Smart Account (ERC-4337) Swaps** - Automated swaps via delegated smart accounts
- **L2 DeFi Applications** - Handling WETH unwrapping and chain-specific patterns

## Quick Start

### Using the Skill

The `swap-integration` skill activates when you mention building swaps or integrating Ring:

```text
"Help me integrate Ring swaps into my frontend"
"Build a swap script that trades USDC for ETH"
"Create a smart contract that executes swaps via Universal Router"
```

### Slash Command

```text
/swap-integration
```

## Supported Protocols

- Ring V2
- Ring V3
- Ring V4
- Universal Router (unified interface for all versions)

## Integration Methods

| Method                    | Best For                                               |
| ------------------------- | ------------------------------------------------------ |
| **Trading API**           | Frontends, backends - handles routing and optimization |
| **Universal Router SDK**  | Direct contract interaction with full control          |
| **Direct Contract Calls** | Smart contract integrations                            |

## Prerequisites

This plugin assumes familiarity with viem basics. Install the **ring-viem** plugin for comprehensive viem/wagmi guidance:

```bash
claude plugin add @ring/ring-viem
```

## License

MIT
