# CLAUDE.md - ring-trading Plugin

## Overview

This plugin provides comprehensive guidance for integrating Ring swaps into frontends, backends, and smart contracts. It supports the Trading API, Universal Router SDK, and direct smart contract integration.

## Plugin Components

### Skills (./skills/)

- **swap-integration**: Comprehensive guide for integrating Ring swaps via Trading API, Universal Router SDK, or direct smart contract calls. Covers frontend hooks, backend scripts, Solidity integrations, Permit2 patterns, ERC-4337 smart account integration, L2 WETH handling, rate limiting, and troubleshooting.
- **pay-with-any-token**: Pay HTTP 402 Payment Required challenges (MPP and x402) by swapping or bridging tokens via the Ring Trading API. Supports WWW-Authenticate header-based and JSON body-based MPP challenges, cross-chain bridging to Tempo, and automatic stablecoin swaps.

### Agents (./agents/)

- **swap-integration-expert**: Expert agent for complex Ring swap integration questions, Trading API debugging, Universal Router encoding, Permit2 patterns, ERC-4337 smart account integration, and L2-specific patterns.

## File Structure

```text
ring-trading/
├── .claude-plugin/
│   └── plugin.json
├── agents/
│   └── swap-integration-expert.md
├── skills/
│   ├── swap-integration/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── advanced-patterns.md
│   └── pay-with-any-token/
│       ├── SKILL.md
│       └── references/
│           ├── trading-api-flows.md
│           └── credential-construction.md
├── project.json
├── package.json
├── CLAUDE.md
└── README.md
```

## Integration Methods

1. **Trading API** (Recommended for most use cases)

   - REST API at `https://trade-api.gateway.ring.org/v1`
   - Handles routing optimization automatically
   - 3-step flow: check_approval -> quote -> swap

2. **Universal Router SDK**

   - Direct SDK usage with `@ring/universal-router-sdk`
   - Full control over transaction construction
   - Command-based architecture

3. **Direct Smart Contract Integration**
   - Solidity contracts calling Universal Router
   - For on-chain integrations and DeFi composability

## Supported Chains

See the [official supported chains list](https://api-docs.ring.org/guides/supported_chains#supported-chains-for-swapping) for the current set of chains supported by the Trading API.

## Related Plugins

- **ring-viem**: Foundational EVM blockchain integration using viem/wagmi (prerequisite knowledge)
- **ring-hooks**: Ring v4 hook development with security-first approach

## Key References

- Trading API: `https://trade-api.gateway.ring.org/v1`
- Universal Router: `github.com/Ring/universal-router`
- SDKs: `@ring/universal-router-sdk`, `@ring/v3-sdk`, `@ring/sdk-core`
- Permit2: Token approval infrastructure
