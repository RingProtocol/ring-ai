# ring-hooks

AI-powered, security-first assistance for creating Ring v4 hooks.

## Overview

This Claude Code plugin provides skills for developing Ring v4 hooks with a strong emphasis on security. It covers custom fee hooks and other advanced hook patterns—all built on a foundation of security best practices.

**Recommended Learning Path**: Complete `v4-security-foundations` before building specific hook types.

## Skills

### v4-security-foundations

Security-first guide for v4 hook development. Covers:

- Threat model framework (5 key threat areas)
- Permission flags risk matrix (all 14 flags)
- NoOp rug pull attack prevention
- Delta accounting fundamentals
- Access control and router verification patterns
- Pre-deployment audit checklist

**Usage:**

```text
/v4-security-foundations
```

Or ask about security:

```text
"What are the security risks of beforeSwapReturnDelta?"
"How do I prevent NoOp attacks in my v4 hook?"
```

## Installation

### Via Skills CLI (Any Agent)

```bash
npx skills add Ring/ring-ai
```

### Via Claude Code Marketplace

```bash
/plugin marketplace add ring/ring-ai
/plugin install ring-hooks
```

## Requirements

- Claude Code with plugin support
- Familiarity with Ring v4 hooks architecture

## Resources

- [Ring v4 Documentation](https://docs.ring.org/contracts/v4/overview)
- [v4 Hooks Guide](https://docs.ring.org/contracts/v4/concepts/hooks)
- [Hook Examples](https://github.com/Ring/v4-periphery/tree/main/src/lens)

## Acknowledgments

The `v4-security-foundations` skill draws inspiration from the community skill at [igoryuzo/uniswapV4-hooks-skill](https://github.com/igoryuzo/uniswapV4-hooks-skill) ([v4hooks.dev](https://www.v4hooks.dev)), which compiled security guidance from Certora/ABDK audit reports, NoOp exploit analysis, and 50+ production hook examples.

## License

MIT License - see [LICENSE](../../../LICENSE) for details.
