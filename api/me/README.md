# Me

## Informationen über den eigenen User

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/me`

Mit dieser Abfrage erhältst du alle relevanten Informationen, die wir über einen User gesammelt haben.

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"user": {
		"userId": "31021656",
		"userName": "thejocraft_live",
		"streamerType": "partner",
		"registered": "2023-05-20T22:25:05.000Z",
		"role": "vip",
		"tier": 3
	},
	"overlays": {
		"game": "GXXXXXXX",
		"tool": "TXXXXXXX",
		"background": "BXXXXXXX",
		"event": "EXXXXXXX"
	},
	"streamdeck": {
		"token": "sliveapp_se_XXXXXXX"
	},
	"selected": {
		"game": "app.slive.game.default",
		"tools": [
			"de.thejocraft.tool.raid",
			"de.thejocraft.tool.clipsViewer"
		],
		"background": "de.thejocraft.background.chat",
		"event": "app.slive.event.default"
	},
	"preAccess": {
		"games": [],
		"tools": [],
		"background": [],
		"events": []
	},
	"favs": {
		"games": [],
		"tools": [],
		"backgrounds": [],
		"events": []
	},
	"twitch": {
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
			"id": "41585752632",
			"status": "live",
			"title": "CRAFT ATTACK 11 | Wir entwickeln eine eigene HOLZFARM",
			"viewer": 677,
			"language": "de",
			"preview": "https://static-cdn.jtvnw.net/previews-ttv/live_user_thejocraft_live-1920x1080.jpg?1703536590410",
			"game": {
				"id": "27471",
				"name": "Minecraft"
			},
			"uptime": {
				"startedAt": "2023-12-25T17:12:50Z",
				"startedAtUnix": 1703524370000,
				"converted": "03:23h"
			},
			"lastStream": {
				"uptime": "",
				"title": "",
				"vod": "",
				"startedAt": ""
			},
			"tags": [],
			"stats": 1703536300330
		}
	}
}
```
{% endcode %}
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{
	"code": 401,
	"message": "Authorization has failed - invalid Bearer token"
}
```
{% endtab %}
{% endtabs %}
