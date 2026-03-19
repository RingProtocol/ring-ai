# Ring Wallet Plugin

AI guidance for integrating DApps into Ring Wallet using the official SDK, EIP-1193/EIP-6963 provider patterns, and iframe embedding requirements.

## Installation

```bash
npx skills add ringprotocol/uniswap-ai --skill dapp-to-ringwallet
```

## Included Skill

| Skill                | Description                                                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `dapp-to-ringwallet` | End-to-end DApp integration flow for Ring Wallet: SDK loading, CSP, provider detection, iframe compatibility, and test workflow |

## Quick Usage

Trigger the skill with prompts like:

```text
Help me integrate my DApp into Ring Wallet
How should I load dappsdk.js and configure CSP?
Why does my DApp fail to open inside Ring Wallet iframe?
```

## Integration Output Coverage

The skill is designed to always cover:

- DApp registration requirements and API key flow
- SDK loading mode (self-host vs wallet-hosted)
- `<script>` placement at the top of `<head>`
- CSP requirements for the selected loading mode
- `window.ethereum` behavior and EIP-6963 discovery
- `X-Frame-Options` compatibility for iframe embedding
- `?testdapp=YOUR_API_KEY` verification workflow

## Reference Specification

Canonical integration specification:

- [references/dapp-integration.md](./references/dapp-integration.md)
