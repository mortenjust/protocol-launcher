# Protocol Linker

Make app deep links clickable on Discord, Telegram, and other platforms that block custom URI schemes.

## The problem

You want to share `obsidian://`, `raycast://`, `things://`, or any app deep link in Discord or Telegram, but they strip anything that isn't `https://`.

## The solution

A tiny redirect. Wrap any app URL as a query parameter:

```
https://yourdomain.com/?url=obsidian%3A%2F%2Fopen%3Fvault%3DX%26file%3DY
```

It redirects to the decoded URL instantly. Works with any protocol.

## Deploy

One static HTML file. No build step, no dependencies.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/mortenjust/protocol-linker)

Or deploy anywhere — just route all paths to `index.html`.

## Agent skill

An agent skill is included so AI agents can generate linker URLs automatically:

```
npx skills add mortenjust/protocol-linker
```
