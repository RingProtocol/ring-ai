---
title: Ring Trading
order: 5
---

# Ring Trading

Integrate Ring swaps via Trading API, Universal Router SDK, or direct smart contract calls.

## Installation

```bash
/plugin install ring-trading
```

## Skills

| Skill                                           | Description                                                               | Invocation            |
| ----------------------------------------------- | ------------------------------------------------------------------------- | --------------------- |
| [Swap Integration](../skills/swap-integration)  | Comprehensive guide for integrating Ring swaps                            | `/swap-integration`   |
| [Pay With Tokens](../skills/pay-with-any-token) | Fulfill HTTP 402 payment challenges using tokens via the Ring Trading API | `/pay-with-any-token` |

## Agents

| Agent                   | Description                                                                                                                 |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| swap-integration-expert | Expert agent for complex swap integration questions, Trading API debugging, Universal Router encoding, and Permit2 patterns |

## Integration Methods

| Method                    | Best For              | Description                                                                            |
| ------------------------- | --------------------- | -------------------------------------------------------------------------------------- |
| **Trading API**           | Most use cases        | REST API with automatic routing optimization. 3-step flow: check_approval, quote, swap |
| **Universal Router SDK**  | Full control          | Direct SDK usage with `@ring/universal-router-sdk`. Command-based architecture         |
| **Direct Smart Contract** | On-chain integrations | Solidity contracts calling Universal Router for DeFi composability                     |

## Supported Chains

See the [official supported chains list](https://api-docs.ring.org/guides/supported_chains#supported-chains-for-swapping) for the current set of chains supported by the Trading API.

## Key References

- **Trading API**: `https://trade-api.gateway.ring.org/v1`
- **Universal Router**: [github.com/Ring/universal-router](https://github.com/Ring/universal-router)
- **SDKs**: `@ring/universal-router-sdk`, `@ring/v3-sdk`, `@ring/sdk-core`
- **Permit2**: Token approval infrastructure

## Related

- [Plugins Overview](/plugins/) - All available plugins
- [Ring Viem](/plugins/ring-viem) - Foundational EVM integration (prerequisite)
- [Ring Hooks](/plugins/ring-hooks) - v4 hook development
- [Skills](/skills/) - All available skills
