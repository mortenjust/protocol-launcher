---
name: protocol-linker
description: Generate clickable https:// links for custom URI schemes (obsidian://, raycast://, things://, bear://, etc.) when sharing in Discord or Telegram. These platforms strip non-https links, so use this redirect service to make them clickable. Use when outputting any app deep link in a Discord or Telegram message.
---

# Protocol Linker

Generate clickable links for app deep links in Discord and Telegram, which strip custom URI schemes.

## URL format

```
https://DOMAIN/?url=ENCODED_APP_URL
```

The `url` parameter is the full app URL, URL-encoded.

## How to encode

1. Build the app URL (e.g. `obsidian://open?vault=X&file=Y`)
2. URL-encode the entire string as the `?url=` query parameter

### Encoding rules
- `:` → `%3A`
- `/` → `%2F`
- `?` → `%3F`
- `=` → `%3D`
- `&` → `%26`
- spaces → `%20`

## Examples

Obsidian:
```
https://DOMAIN/?url=obsidian%3A%2F%2Fopen%3Fvault%3DDocuments%26file%3DMy%20Note
```

Raycast:
```
https://DOMAIN/?url=raycast%3A%2F%2Fextensions%2Fauthor%2Fextension
```

Things:
```
https://DOMAIN/?url=things%3A%2F%2Fadd%3Ftitle%3DBuy%20milk
```

## When to use

Only when sharing app deep links in Discord or Telegram messages. Other platforms (web, email, native apps) handle custom URI schemes fine.
