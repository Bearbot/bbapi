# General Operations

These are just general operations for Bearbot. __(WIP)__

---
## `GET /config`
Returns the current configuration for Bearbot.

A response will look like this:
```json
{
  "token": "XXXXXXXXXXX",
  "lfmtoken": "XXXXXXXXXXXXXXX",
  "botSettings": {
    "setGameOnStart": true,
    "gamesRoll": [
      "bear videos",
      "grrrrr"
    ],
    "defaultPresence": "WATCHING"
  }
}
```
