# Obsidian Launcher

A tiny web redirect that opens `obsidian://` URLs from places that don't support custom URI schemes (Discord, Slack, etc.).

## Usage

Append any Obsidian URI path after the domain:

```
https://yourdomain.com/open?vault=MyVault&file=My%20Note
```

This redirects to:

```
obsidian://open?vault=MyVault&file=My%20Note
```

## Deploy

Deploy to Vercel — it's a single static HTML file with a catch-all rewrite.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/mortenjust/obsidian-launcher)

## How it works

1. Takes everything after the domain as the Obsidian URI path
2. Prepends `obsidian://`
3. Auto-redirects (with a fallback button)

No server, no dependencies, no build step.
