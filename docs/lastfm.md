# Last.fm

_WIP_

Keep in mind that error codes and API responses listed here are subject to change at any time during the development cycle.

## `GET /lfm/get/:id`
when a Discord user ID is provided, the API will look up the user ID in it's database.

### Responses

If it finds the user ID in the database, you will get a response like this:
```json
{
    "username": "username"
}
```

If the database query returns nothing, you'll get an error like this:
```json
{
    "errorCode": 101,
    "error": "User ID not in database."
}
```

## `GET /lfm/scrobbling/:name`

This route will take the provided Last.fm name and see if anything is being scrobbled by the user.

### Responses

If something is being scrobbled, you'll get a response like this:
```json
{
    "songTitle": "Feel It Still",
    "songArtist": "Portugal. The Man",
    "albumArt": {
        "high": "https://url.here/album_art_high.png",
        "medium": "https://url.here/album_art_medium.png",
        "low": "https://url.here/album_art_low.png"
    },
    "lfmUrl": "https://last.fm/link/here"
}
```

If the username is found, but nothing is being scrobbled, you'll get a response like this:
```json
{
    "errorCode": 102,
    "error": "User is not scrobbling anything."
}
```

If the username is not found, you'll get a response like this:
```json
{
    "errorCode": 103,
    "error": "Username not found."
}
```

## `GET /lfm/profile/:name`

Returns profile info for a username.

### Responses

If the user is found **and** is scrobbling something, you'll get a response like this:
```json
{
    "username": "usernameHere",
    "profilePictures": {
        "high": "https://url.here/profile_picture_high.png",
        "medium": "https://url.here/profile_picture_medium.png",
        "low": "https://url.here/profile_picture_low.png"
    },
    "scrobbles": 5900,
    "scrobbling": {
        "songTitle": "Feel It Still",
        "songArtist": "Portugal. The Man",
        "albumArt": {
            "high": "https://url.here/album_art_high.png",
            "medium": "https://url.here/album_art_medium.png",
            "low": "https://url.here/album_art_low.png"
        },
        "lfmUrl": "https://last.fm/link/here"
    }
}
```

If the user is found but is not scrobbling anything, you'll get a response like this:
```json
{
    "username": "usernameHere",
    "profilePictures": {
        "high": "https://url.here/profile_picture_high.png",
        "medium": "https://url.here/profile_picture_medium.png",
        "low": "https://url.here/profile_picture_low.png"
    },
    "scrobbles": 5900
}
```

If the user is not found, you'll get a response like this:
```json
{
    "errorCode": 104,
    "error": "Username not found."
}
```

## `GET /lfm/recent/:name/:limit`

Returns recent songs with a limit.
