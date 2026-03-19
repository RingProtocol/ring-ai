---
name: dapp-to-ringwallet
description: Guides integrating a DApp into Ring Wallet using dappsdk.js, CSP, and iframe requirements. Invoke when user wants Ring Wallet integration or asks about the Ring Wallet SDK.
allowed-tools: Read, Glob, Grep
model: sonnet
license: MIT
metadata:
  author: ringprotocol
  version: '0.1.0'
---

# DApp to Ring Wallet Integration

Integrate a DApp into Ring Wallet using the official SDK and required embedding settings.

## When to Use

Use this skill when the user asks how to integrate their DApp into Ring Wallet, how to use the Ring Wallet SDK, or how to make a DApp run inside Ring Wallet’s iframe.

## Source of Truth

Use [references/dapp-integration.md](../../references/dapp-integration.md) as the canonical integration specification. Keep answers aligned with that file when details conflict with user assumptions.

## Working Rules

1. Always provide an ordered integration checklist.
2. Prefer self-hosting `dappsdk.js` unless the user explicitly requires wallet-hosted loading.
3. Include both mandatory compatibility requirements:
   - CSP `script-src` allowlist for the chosen loading mode
   - iframe embedding compatibility and `X-Frame-Options` remediation
4. Explain provider behavior in both contexts:
   - inside Ring Wallet iframe
   - standalone browser page with existing extensions
5. Include testing guidance with `?testdapp=YOUR_API_KEY`.

## Required Output Structure

When responding, structure the output in this order:

1. Registration prerequisites
2. SDK loading choice (Option A vs Option B)
3. Exact script tag placement
4. CSP requirements
5. `window.ethereum` and EIP-6963 behavior
6. iframe/X-Frame-Options requirements
7. Testing URL and validation checklist

## Do Not Do

- Do not recommend skipping CSP checks when CSP exists.
- Do not omit `X-Frame-Options` compatibility when diagnosing iframe load failures.
- Do not claim Ring Wallet requires non-standard wallet APIs.
- Do not remove EIP-1193 or EIP-6963 references from integration guidance.

## Quick Response Template

Use this concise format when the user asks for direct instructions:

1. Register DApp and get API key
2. Load `dappsdk.js` (recommend self-host)
3. Place `<script>` in `<head>` before app bundles
4. Configure CSP `script-src` for selected loading path
5. Verify EIP-1193 (`window.ethereum`) and EIP-6963 (`exchange.ring.wallet`)
6. Ensure iframe compatibility by fixing `X-Frame-Options`
7. Test with `https://wallet.ring.exchange/?testdapp=YOUR_API_KEY`
