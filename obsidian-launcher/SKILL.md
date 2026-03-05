---
name: obsidian-launcher
description: Generate clickable Obsidian links for platforms that block custom URI schemes (Discord, Slack, etc.). Use when sharing Obsidian note links in chat messages, Linear issues, or anywhere obsidian:// URLs don't work. Uses a protocol launcher redirect service to convert obsidian:// URIs to clickable https:// URLs.
---

# Obsidian Launcher

Generate clickable links to Obsidian notes for platforms that strip `obsidian://` custom URI schemes.

## URL format

```
https://DOMAIN/?url=ENCODED_OBSIDIAN_URL
```

The `url` parameter must be fully URL-encoded.

## How to encode

1. Build the Obsidian URL: `obsidian://open?vault=VAULT&file=PATH`
2. URL-encode the entire thing as the `url` query parameter

### Encoding rules
- `:` → `%3A`
- `/` → `%2F`
- `?` → `%3F`
- `=` → `%3D`
- `&` → `%26`
- spaces → `%20`

## Example

Note: `Morten/SpriteKit Desktop Physics Demo` in vault `Documents`

Obsidian URL:
```
obsidian://open?vault=Documents&file=Morten/SpriteKit%20Desktop%20Physics%20Demo
```

Launcher URL:
```
https://DOMAIN/?url=obsidian%3A%2F%2Fopen%3Fvault%3DDocuments%26file%3DMorten%2FSpriteKit%2520Desktop%2520Physics%2520Demo
```

## When to use

Include a launcher link whenever creating or editing an Obsidian note and sharing the result in Discord, Slack, Telegram, or any platform that doesn't support `obsidian://` URIs.
