# А-race.3d

Tron-style neon runner with **skin shop** and **Telegram account binding**.

## Play

Upload `index.html` / `A-race.3d.html` to GitHub Pages root.

https://neonkotick.github.io/A-race.3d/

## Features

- 6 light-cycle skins (shop, buy with ◆ crystals)
- Progress bound to Telegram user id (`localStorage` key `arace3d_acc_<id>`)
- `window.ARaceAPI` for bot backend integration
- Telegram WebApp SDK (`tg.ready`, expand, haptic)

## Telegram Mini App + Bot

1. Host on HTTPS (GitHub Pages)
2. BotFather → `/newbot` → `/newapp` → set Web App URL
3. Optional backend: listen for scores via `ARaceAPI.submitScore(url)` or `ARaceOnSave` hook

### Client API

```js
ARaceAPI.getUser()
ARaceAPI.getAccount()
ARaceAPI.getPayload()      // includes initData for server validation
ARaceAPI.setCloudAccount(data)
ARaceAPI.submitScore('https://your.api/score')
```

Validate `initData` on the server with the bot token (HMAC) before trusting scores.
