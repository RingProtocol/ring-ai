---
title: DApp to Ring Wallet
order: 2
---

# DApp to Ring Wallet

Integrate a DApp into Ring Wallet iframe runtime by loading `dappsdk.js` and configuring CSP correctly.

## Invocation

```text
/dapp-to-ringwallet
```

Or describe your requirements naturally:

```text
帮我把 DApp 接入 Ring Wallet，并修复 iframe 打开失败问题
```

## What It Does

This skill helps you:

- **Add SDK initialization**: Inject `https://wallet.ring.exchange/dappsdk.js` before app scripts so EIP-1193 and EIP-6963 are available early
- **Configure CSP script source**: Ensure `script-src` allows the Ring Wallet SDK domain
- **Enable iframe embedding**: Add `frame-ancestors 'self' https://wallet.ring.exchange` through HTTP response headers
- **Fix deployment headers**: Update Vercel, Netlify, or equivalent deployment config for CSP compatibility
- **Remove blocking headers**: Replace `X-Frame-Options` restrictions with CSP `frame-ancestors`

## Required Changes

Both changes are mandatory:

1. **Load `dappsdk.js` in HTML `<head>`** before app bundle scripts
2. **Set CSP correctly** for both `script-src` and `frame-ancestors`

## Validation Checklist

- `window.ethereum.isRingWallet === true` inside Ring Wallet iframe
- Wallet connection (`eth_requestAccounts`) works
- Transaction signing and chain switching events work
- DApp is embeddable at `https://wallet.ring.exchange/?testdapp=YOUR_API_KEY`

## Runtime Compatibility

This skill can run with or without interactive prompts. If interactive question tools are unavailable, it collects required integration details through natural language conversation.

## Related Resources

- [ring-wallet Plugin](/plugins/ring-wallet) - Parent plugin
- [Skills Overview](/skills/) - Browse all available skills
- [Ring Wallet Test URL](https://wallet.ring.exchange/?testdapp=YOUR_API_KEY) - Integration verification
