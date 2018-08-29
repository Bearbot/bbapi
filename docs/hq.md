# HQ

The latest game show craze, live on your phone!

---
## `GET /shows/isLive"
Checks if a show is live.

If a show is live, you'll get a response like this:
```json
{
  "live": true,
  "vertical": "general",
  "prize": "$5,000",
  "streamUrls: {
    "low": "XXXXXXXXXXX",
    "medium": "XXXXXXXXXXXXXXXXX",
    "high": "XXXXXXXXXXXXXXXXXXXXXXXX",
    "source": "XXXXXXXXXXXXXXXXXXXXXXXXXXX"
  }
}
```

If a show is not live, you'll get a response like this:
```json
{
  "live": false,
  "nextVertical": "general"
  "time": "XXXXXXXXXXX",
  "nextPrize": "$5,000"
}
```
