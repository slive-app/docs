# Chat

Sobald eine Chatnachricht erscheint, senden wir dir diese Information. Wir haben allerdings ein paar Kleinigkeiten geändert, die Twitch nicht bedacht hat.

{% hint style="info" %}
Wir nutzen die offiziellen Daten von Twitch, fügen aber ein paar eigene Sachen hinzu. Für mehr Informationen, schaut daher bei den Docs von Twitch nach: [https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/#channelchatmessage](https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/#channelchatmessage)
{% endhint %}

<details>

<summary>Event Object</summary>

<pre class="language-json"><code class="lang-json">{
    "ID": "OB2OF_CHAT",
    "CODE": 200,
    "MESSAGE": "A wild chat message appeared!",
    "DATA": {
    "broadcaster_user_id": "1971641",
    "broadcaster_user_login": "streamer",
    "broadcaster_user_name": "streamer",
    "chatter_user_id": "4145994",
    "chatter_user_login": "viewer32",
    "chatter_user_name": "viewer32",
    "message_id": "cc106a89-1814-919d-454c-f4f2f970aae7",
    "message": {
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
    "control": <a data-footnote-ref href="#user-content-fn-1">"none"</a>
  }
}
</code></pre>

</details>

[^1]: slive konventiert die Nachricht des Users automatisch zu einem Control-Wert, der von Spielen zur Steuerung genutzt werden kann.\
    \
    Mögliche Werte:\
    "none", "up", "down", "left", "right"
