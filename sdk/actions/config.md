# Config

## .set(json)

Damit dein Modul von unserem System richtig erkannt wird, benötigt die SDK ein paar Informationen von dir. Führe die Funktion `SLIVE.config.set()` so früh es geht auf, da sonst die Verbindung zum Backend geschlossen wird.&#x20;

<pre class="language-javascript" data-line-numbers data-full-width="false"><code class="lang-javascript">SLIVE.config.set({
    id: "<a data-footnote-ref href="#user-content-fn-1">app.slive.sdk.test</a>",
    name: "<a data-footnote-ref href="#user-content-fn-2">Overlay Test</a>",
    width: <a data-footnote-ref href="#user-content-fn-3">1920</a>,
    height: <a data-footnote-ref href="#user-content-fn-4">1080</a>
})
</code></pre>

| Key    | Type   | Funktion                   |
| ------ | ------ | -------------------------- |
| id     | String | Identifier als Reverse-DNS |
| name   | String | Name deines Overlays       |
| width  | Int    | Breite in Pixel            |
| height | Int    | Höhe in Pixel              |

Die SDK nutzt diese Informationen, um z.b. dein Overlay an das Display vom Streamer anzupassen.

***

## .get()

Um die Informationen zu erhalten, die von slive lokal abgespeichert wurden, kannst du `SLIVE.config.get()` aufrufen. Dieser gibt eine JSON zurück, die ungefähr so aussieht:

<details>

<summary>SLIVE.config.get()</summary>

```json
{
  "connection": {
    "id": "b4a8100e-1a97-42b2-ad14-1992bd16fe2e",
    "status": "connected",
    "authed": true,
    "type": "overlay"
  },
  "overlay": {
    "token": "Eabcdefgxxxx",
    "type": "event",
    "selectedId": "app.slive.event.thejocraft.diawars2",
    "selectedIds": false,
    "name": "DiaWars #2",
    "host": "https://beta.slive.app"
  },
  "api": {
    "host": "https://apibeta.slive.app",
    "token": "Aabcdefgxxxx"
  },
  "slive": {
    "tier": 3
  },
  "twitch": {
    "user": {
      "id": "196019423",
      "name": "KaiSchallenberg",
      "userType": "",
      "broadcasterType": "affiliate",
      "views": 0,
      "description": "Lost. | slive | Twitch-Nerd",
      "pb": "https://static-cdn.jtvnw.net/jtv_user_pictures/cf4b1d8a-969d-4d21-b3ff-4ac7cdd5f485-profile_image-300x300.png",
      "offlineImg": "https://static-cdn.jtvnw.net/jtv_user_pictures/e86e12c0-9546-4f86-acef-b30678a50481-channel_offline_image-1920x1080.png",
      "isBanned": false,
      "bannedSince": 0
    },
    "stream": {
      "id": "",
      "status": "offline",
      "title": "",
      "viewer": 0,
      "language": "",
      "preview": "",
      "game": {
        "id": "",
        "name": ""
      },
      "uptime": {
        "startedAt": "",
        "startedAtUnix": "",
        "converted": ""
      },
      "tags": [],
      "lastStream": {
        "uptime": "",
        "title": "",
        "vod": "",
        "startedAt": ""
      },
      "stats": false
    },
    "slive": {
      "badge": []
    },
    "scopes": [
      "bits:read",
      "channel:read:charity",
      "channel:read:goals",
      "channel:read:hype_train",
      "channel:read:polls",
      "channel:read:predictions",
      "channel:read:subscriptions",
      "moderation:read",
      "moderator:read:followers",
      "moderator:read:shoutouts",
      "user:read:chat"
    ]
  }
}
```

</details>

Um also auf deinen Usernamen zu kommen, kannst du direkt `SLIVE.config.get().twitch.user.name` nehmen.

[^1]: Deine ID als Reverse-DNS

[^2]: Ein Name, der im Controller angezeigt werden kann

[^3]: Breite in Pixel

[^4]: Höhe in Pixel
