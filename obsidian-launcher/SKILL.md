---
name: obsidian-launcher
description: Generate clickable Obsidian links for platforms that block custom URI schemes (Discord, Slack, etc.). Use when sharing Obsidian note links in chat messages, Linear issues, or anywhere obsidian:// URLs don't work. Converts obsidian:// URIs to https:// URLs via a redirect service.
---

# Obsidian Launcher

Generate clickable links to Obsidian notes for platforms that strip `obsidian://` custom URI schemes.

## URL format

```
https://DOMAIN/open?vault=VAULT_NAME&file=PATH_TO_NOTE
```

This redirects to `obsidian://open?vault=VAULT_NAME&file=PATH_TO_NOTE`.

## Rules

- URL-encode spaces as `%20` in file paths
- File path is relative to vault root (e.g. `Morten/My%20Note`)
- No `.md` extension needed
- Always use `https://` (not `http://`)

## Example

For a note at `Morten/SpriteKit Desktop Physics Demo` in vault `Documents`:

```
https://DOMAIN/open?vault=Documents&file=Morten/SpriteKit%20Desktop%20Physics%20Demo
```

## When to use

Include a launcher link whenever creating or editing an Obsidian note and sharing the result in a chat message, issue tracker, or any platform that doesn't support `obsidian://` URIs.
