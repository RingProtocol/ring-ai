---
title: Installation
order: 2
---

# Installation

Multiple installation options are available depending on your use case.

## Claude Code Plugin

### Via Marketplace

Install all plugins from the Claude Code Marketplace:

```bash
/plugin marketplace add ringprotocol/ring-ai
```

### Install Individual Plugins

```bash
/plugin install ring-trading       # Swap integration
/plugin install ring-driver        # Swap & liquidity planning
```

## Development Setup

To contribute or develop locally:

```bash
# Clone the repository
git clone https://github.com/ringprotocol/ring-ai.git
cd ring-ai

# Install dependencies
npm install

# Build all packages
npx nx run-many -t build

# Run tests
npx nx run-many -t test
```

## System Requirements

| Requirement | Version | Purpose           |
| ----------- | ------- | ----------------- |
| Claude Code | Latest  | Plugin runtime    |
| Node.js     | 22.x    | Local development |
| npm         | 11.7.0+ | Local development |

### npm Version (for contributors)

Local development requires npm 11.7.0+:

```bash
npm install -g npm@latest
npm --version  # Should output: 11.7.0 or higher
```

## Verifying Installation

After plugin installation, the plugin's skills should be available as slash commands. For example, after installing `ring-wallet`:

```text
/ring-wallet
```

## Troubleshooting

### Plugin Not Found

If skills don't appear after installation:

1. Verify the plugin was installed successfully
2. Try reinstalling with `/plugin install <plugin-name>`
3. Check that Claude Code is up to date
