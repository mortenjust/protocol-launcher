# Obsidian Launcher

Open Obsidian notes from Discord, Slack, and other platforms that block `obsidian://` custom URI schemes.

## The problem

You want to share a link to an Obsidian note in Discord or Slack, but these platforms strip custom URI schemes. Only `https://` links are clickable.

## The solution

Deploy this tiny redirect service. It takes an `https://` URL and redirects to the equivalent `obsidian://` URL.

```
https://yourdomain.com/open?vault=MyVault&file=My%20Note
                          ↓
        obsidian://open?vault=MyVault&file=My%20Note
```

Auto-redirects instantly, with a fallback button if the browser blocks it.

## Deploy

One static HTML file. No build step, no dependencies, no server.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/mortenjust/obsidian-launcher)

Or deploy anywhere that serves static files — just make sure all paths route to `index.html` (see `vercel.json` for the rewrite rule).

## For AI agents

The `obsidian-launcher/` folder contains an [agent skill](https://github.com/openai/codex) that teaches AI coding agents to generate clickable Obsidian links in chat platforms. Install the skill and set your domain.
