---
title: Ring Driver
order: 7
---

# Ring Driver

AI-powered assistance for discovering tokens, planning Ring swaps and liquidity positions, and generating deep links.

## Installation

```bash
/plugin install ring-driver
```

## Skills

| Skill                                            | Description                                                | Invocation           |
| ------------------------------------------------ | ---------------------------------------------------------- | -------------------- |
| [Swap Planner](../skills/swap-planner)           | Plan and generate deep links for token swaps               | `/swap-planner`      |
| [Liquidity Planner](../skills/liquidity-planner) | Plan and generate deep links for LP positions (v2, v3, v4) | `/liquidity-planner` |

## Deep Link URL Structures

### Swap Deep Links

Base URL: `https://app.ring.org/swap`

| Parameter        | Description                      | Example                        |
| ---------------- | -------------------------------- | ------------------------------ |
| `chain`          | Network name                     | `ethereum`, `base`, `arbitrum` |
| `inputCurrency`  | Input token address or "NATIVE"  | `0xA0b8...` or `NATIVE`        |
| `outputCurrency` | Output token address or "NATIVE" | `0xA0b8...` or `NATIVE`        |
| `value`          | Amount to swap                   | `1.5`                          |
| `field`          | Which field the value applies to | `INPUT` or `OUTPUT`            |

### Liquidity Deep Links

Base URL: `https://app.ring.org/positions/create`

| Parameter   | Description                | Example                               |
| ----------- | -------------------------- | ------------------------------------- |
| `chain`     | Network name               | `ethereum`, `base`                    |
| `currencyA` | First token address        | `0xA0b8...` or `NATIVE`               |
| `currencyB` | Second token address       | `0xA0b8...`                           |
| `fee`       | JSON with fee tier         | `{"feeAmount":3000,"tickSpacing":60}` |
| `hook`      | v4 hook address (optional) | `0x...`                               |

## Chain Names

| Chain       | URL Parameter |
| ----------- | ------------- |
| Ethereum    | `ethereum`    |
| Base        | `base`        |
| Arbitrum    | `arbitrum`    |
| Optimism    | `optimism`    |
| Polygon     | `polygon`     |
| BNB Chain   | `bnb`         |
| Avalanche   | `avalanche`   |
| Celo        | `celo`        |
| Blast       | `blast`       |
| Zora        | `zora`        |
| World Chain | `worldchain`  |
| Unichain    | `unichain`    |

## Output Format

Skills output a summary of the operation, a clickable deep link URL, and any relevant warnings. The deep link opens directly in the Ring web interface with pre-filled parameters.

## Related

- [Plugins Overview](/plugins/) - All available plugins
- [Skills](/skills/) - All available skills
- [Ring Interface](https://app.ring.org)
- [Ring Docs](https://docs.ring.org)
