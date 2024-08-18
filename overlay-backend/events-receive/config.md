# Config

Unmittelbar nach dem erfolgreichen Aufbau der Verbindung erhältst du von uns die Config. Diese ändert sich leicht je nach Typ des bereitgestellten Tokens.

<details>

<summary>Event Object</summary>

<pre class="language-json"><code class="lang-json">{
    "ID": "OB2OF_CONFIG",
    "CODE": 200,
    "MESSAGE": "Config Data for Overlay",
    "DATA": {
        "connection": {
            "id": <a data-footnote-ref href="#user-content-fn-1">"1d15714a-718b-4f78-9c3c-6e69bfdcd338"</a>,
            "status": "connected",
            "authed": true
        },
        "overlay": {
            "token": <a data-footnote-ref href="#user-content-fn-2">"XXXXXXX"</a>,
            "type": <a data-footnote-ref href="#user-content-fn-3">"game"</a>,
            "selectedId": <a data-footnote-ref href="#user-content-fn-4">"g251a"</a>,
            "selectedIds": <a data-footnote-ref href="#user-content-fn-5">false</a>,
            "name": <a data-footnote-ref href="#user-content-fn-6">"Villager"</a>,
            "settings": [{}], // deprecated
            "host": <a data-footnote-ref href="#user-content-fn-7">"https://beta.slive.app/"</a>
        },
        "slive": {
            "tier": <a data-footnote-ref href="#user-content-fn-8">0</a>
        },
        "<a data-footnote-ref href="#user-content-fn-9">twitch</a>": {
            "user": {
                "id": "31021656",
                "name": "thejocraft_live",
                "userType": "",
                "broadcasterType": "partner",
                "views": 9940437,
                "description": "Minecraft mit Niveau und Verstand neu erfahren. ",
                "pb": "https://static-cdn.jtvnw.net/jtv_user_pictures/449e0a0a-3400-4370-829c-3c93a111ba82-profile_image-300x300.png",
                "offlineImg": "https://static-cdn.jtvnw.net/jtv_user_pictures/8bddf92f-0658-4248-81ec-25af5258fbf2-channel_offline_image-1920x1080.png",
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
                "badge": [] // deprecated
            },
            "scopes": [
                "bits:read",
                "channel:read:goals",
                "channel:read:hype_train",
                "channel:read:polls",
                "channel:read:predictions",
                "channel:read:subscriptions",
                "chat:read",
                "moderator:read:followers",
                "moderator:read:shoutouts"
            ]
        }
    }
}

</code></pre>

</details>

Die Einstellungen werden genutzt, um die einzelnen Module zu laden. Zusätzlich erhält man direkt Informationen über den zugehörigen Twitch-Account.

[^1]: Identifier für die Verbindung

[^2]: Dein bereitgestellter Token

[^3]: Typ des Tokens (game, tool, background, event)

[^4]: Vom User ausgewähltee Modul, sonst false.



    Nur bei Type game, background und event

[^5]: Vom User ausgewählte Module, sonst false.



    Nur bei Type "tool"

[^6]: Name des ausgewählten Moduls

[^7]: Welche Website für die Abwicklung verantwortlich ist

[^8]: 0 = Free\
    1 = Basic\
    2 = Premium\
    3 = Ultra

[^9]: sliveBot ist für dieses Objekt verantwortlich.
