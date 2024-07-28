# Chat

<pre class="language-javascript"><code class="lang-javascript"><strong>SLIVE.on('chat', (data) => {})
</strong></code></pre>

Jede Nachricht, die in den Chat geschrieben wird, löst dieses Event aus. Die Informationen, die du dabei von uns erhältst, sind nahezu identisch zu denen von Twitch. Wir passen jediglich Kleinigkeiten an, die Twitch nicht berücksichtigt hat.

{% hint style="info" %}
Wir nutzen die offiziellen Daten von Twitch. Für mehr Informationen solltet ihr euch daher unbedingt die Docs durchlesen: [https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/#channelchatmessage](https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/#channelchatmessage)
{% endhint %}

```json
 {
      "text": "Hi chat",
      "fragments": [
        {
          "type": "text",
          "text": "Hi chat",
          "cheermote": null,
          "emote": null,
          "mention": null
        }
      ]
    },
    "color": "#00FF7F",
    "badges": [
      {
        "set_id": "moderator",
        "id": "1",
        "info": ""
      },
      {
        "set_id": "subscriber",
        "id": "12",
        "info": "16"
      },
      {
        "set_id": "sub-gifter",
        "id": "1",
        "info": ""
      }
    ],
    "message_type": "text",
    "cheer": null,
    "reply": null,
    "channel_points_custom_reward_id": null,
    "isMod": true,
    "isSub": true,
    "isVip": false,
    "isBroadcaster": false,
    "isFounder": false,
    "isArtist": false,
    "control": "none"
  }
```

| Key     | Änderung                                                                                                                                                                                                                                                                           |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| isMod   | Wenn der Streamer selbst schreibt, war dieser Wert immer `false`. Dieser wird von uns auf `true` gestellt.                                                                                                                                                                         |
| control | <p>slive konventiert die Eingabe des Users in einheitliche Kontroll-Werte um, die das Modul nutzen kann, um z.b. einen Spieler zu steuern. <br><br>Mögliche Werte sind: "<code>none</code>", "<code>up</code>", "<code>down</code>", "<code>left</code>", "<code>right</code>"</p> |
