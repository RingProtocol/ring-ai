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

## Required Inputs to Collect

- DApp name
- DApp URL
- DApp logo (256×256 PNG or SVG)
- Ring Wallet host URL (default is <https://wallet.ring.exchange>)
- API key for testing (provided by Ring Wallet team)

## Integration Steps

### 1. Register the DApp

Ask the user to contact the Ring Wallet team and provide:

- DApp name
- Logo (256×256 PNG or SVG)
- DApp URL

They will receive an API key (UUID) for testing.

### 2. Integrate the SDK

The SDK source of truth in this repo is `public/dappsdk.js` and is served as `/dappsdk.js` in the wallet. All injection and path references are wired through `src/server/dappsdk.ts`. When the SDK changes, only edit `public/dappsdk.js`.

Choose one of two loading options.

#### Option A: Self-host (recommended)

Copy `public/dappsdk.js` into the DApp’s static/public directory and load it from `/dappsdk.js`.

| Framework   | Location               |
| ----------- | ---------------------- |
| Plain HTML  | Same directory as HTML |
| React (CRA) | public/dappsdk.js      |
| Next.js     | public/dappsdk.js      |
| Vue (Vite)  | public/dappsdk.js      |

#### Option B: Load from Ring Wallet

Use the wallet host URL, for example `https://wallet.ring.exchange/dappsdk.js`.

### 3. Add the Script Tag

Add the script tag at the top of `<head>` before app bundles.

```html
<head>
  <script src="/dappsdk.js"></script>
</head>
```

If loading from the wallet host, use:

```html
<head>
  <script src="https://wallet.ring.exchange/dappsdk.js"></script>
</head>
```

Next.js App Router example:

```tsx
export default function RootLayout({ children }) {
  return (
    <html>
      <head>
        <script src="/dappsdk.js" />
      </head>
      <body>{children}</body>
    </html>
  );
}
```

Next.js Pages Router example:

```tsx
import { Html, Head, Main, NextScript } from 'next/document';

export default function Document() {
  return (
    <Html>
      <Head>
        <script src="/dappsdk.js" />
      </Head>
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  );
}
```

### 4. CSP Allowlist

If the DApp uses Content-Security-Policy, ensure the SDK script is allowed.

Self-hosted:

```text
script-src 'self' 'unsafe-inline';
```

Loaded from Ring Wallet:

```text
script-src 'self' https://wallet.ring.exchange
```

If there is no CSP, no change is needed.

### 5. What the SDK Injects

The SDK injects an EIP-1193 provider at `window.ethereum` and announces via EIP-6963.

Provider identification:

```javascript
window.ethereum;
window.ethereum.isRingWallet;
```

Detect Ring Wallet via EIP-6963:

```javascript
window.addEventListener('eip6963:announceProvider', (event) => {
  if (event.detail.info.rdns === 'exchange.ring.wallet') {
    const provider = event.detail.provider;
  }
});
window.dispatchEvent(new Event('eip6963:requestProvider'));
```

Check if running inside Ring Wallet:

```javascript
function isInRingWallet() {
  return !!(window.ethereum && window.ethereum.isRingWallet);
}
```

SDK behavior rules:

- In Ring Wallet’s iframe, the SDK always overrides `window.ethereum`
- As a standalone page, the SDK only injects if `window.ethereum` is not already present

### 6. Allow Iframe Embedding

Ring Wallet loads DApps in an iframe. Ensure your server does not send:

- `X-Frame-Options: DENY`
- `X-Frame-Options: SAMEORIGIN`

Adjust headers in the framework or CDN so embedding is allowed.

### 7. Test the Integration

Open Ring Wallet with the test key:

```text
https://wallet.ring.exchange/?testdapp=YOUR_API_KEY
```

Example:

```text
http://localhost:3000/?testdapp=a3f2b1c8-9d4e-4f5a-b6c7-1234567890ab
```

Verification checklist:

- Wallet connect dialog appears
- Transactions trigger confirmation dialog
- Signature requests work
- Rejecting a request returns an error
