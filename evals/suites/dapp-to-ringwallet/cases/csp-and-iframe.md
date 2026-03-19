# CSP and Iframe Issues

Our DApp fails to load inside Ring Wallet. We suspect CSP and iframe restrictions.

## Context

- The DApp sets Content-Security-Policy headers
- The server currently sends X-Frame-Options: SAMEORIGIN
- The team wants exact fixes and where to apply them

## Requirements

1. Show the CSP directives required when self-hosting and when loading from Ring Wallet
2. Explain why X-Frame-Options blocks Ring Wallet and how to fix it
3. Mention that the SDK should be loaded in the head before app bundles
4. Provide the test URL format with testdapp

## Expected Output

A short remediation guide tailored for CSP and iframe embedding issues.
