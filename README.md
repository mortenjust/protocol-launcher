# Protocol Launcher

Open app deep links from Discord, Slack, and other platforms that block custom URI schemes.

## The problem

You want to share a link like `obsidian://open?vault=X&file=Y` or `raycast://extensions/...` in Discord or Slack, but these platforms strip anything that isn't `https://`.

## The solution

A tiny redirect service. Wrap any app URL in a query parameter:

```
https://yourdomain.com/?url=obsidian%3A%2F%2Fopen%3Fvault%3DX%26file%3DY
```

It auto-redirects to the decoded URL. Works with any protocol: `obsidian://`, `raycast://`, `things://`, `notion://`, `bear://`, `shortcuts://`, etc.

## Deploy

One static HTML file. No build step, no dependencies.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/mortenjust/protocol-launcher)

Or deploy anywhere — just route all paths to `index.html`.

## For AI agents

The `obsidian-launcher/` folder contains an [agent skill](https://clawhub.com) that teaches AI agents to generate clickable Obsidian links in chat platforms. Adapt for other protocols as needed.
