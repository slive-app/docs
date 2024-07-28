# Live

In diesem Teil konzentrieren wir uns auf Daten, die während eines Streams in unserem System angekommen sind. In den Querys könnt ihr dazu noch bestimmte Filter benutzen.&#x20;

{% hint style="warning" %}
sliveApp speichert pro Event-Kategorie nur die neusten 1000 Ereignisse ab.
{% endhint %}

{% hint style="info" %}
Die eingetragenen Werte stammen aus den Eventsubs von Twitch. Für mehr Informationen lohnt es sich, in die offizielle Dokumentation zu schauen: [https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/](https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/)
{% endhint %}

## Erhalte Stream-Infos

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/me/live/stream`

Mit diesem Endpoint erhältst du Informationen zu einem User, seinen Streamdaten und den Stats des aktuellen Streams

#### Query Parameters

| Name  | Type   | Description                                                   |
| ----- | ------ | ------------------------------------------------------------- |
| stats | Bool   | Lasse dir zusätzliche Stats des Streams anzeigen              |
| user  | String | Gebe eine UserId oder den UserName eines anderen Streamers an |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"user": {
		"id": "50985620",
		"name": "Papaplatte",
		"userType": "",
		"broadcasterType": "partner",
		"views": 92766624,
		"description": "der dümmste streamer auf ganz twitch imagine subbing to papaplatte OMEGALUL so trash unlustig unkreativ nicht gut in video spielen, wer hier sein geld lässt ist einfach nur dämlich",
		"pb": "https://static-cdn.jtvnw.net/jtv_user_pictures/04abc1b4-7bad-4b55-8da8-c0f1cf031bda-profile_image-300x300.png",
		"offlineImg": "https://static-cdn.jtvnw.net/jtv_user_pictures/712ebbeb-2bdf-4d67-8159-d6d27752c791-channel_offline_image-1920x1080.jpeg",
		"isBanned": false,
		"bannedSince": 0
	},
	"stream": {
		"id": "43467822507",
		"status": "live",
		"title": "UNSERE MÄDELS KOMMEN // WIR KOCHEN // 7VSWILD WATCHPARTY LETZTE FOLGE // SNOWTRIP TAG 8",
		"viewer": 29879,
		"language": "de",
		"preview": "https://static-cdn.jtvnw.net/previews-ttv/live_user_papaplatte-1920x1080.jpg?1705856711426",
		"game": {
			"id": "509658",
			"name": "Just Chatting"
		},
		"uptime": {
			"startedAt": "2024-01-21T16:25:49Z",
			"startedAtUnix": 1705854349000,
			"converted": "00:39h"
		},
		"lastStream": {
			"uptime": "",
			"title": "",
			"vod": "",
			"startedAt": ""
		},
		"tags": [],
		"stats": [
			{
				"id": "1705854371486-0",
				"message": {
					"timestamp": "1705854371444",
					"viewer": "0",
					"gameName": "Just Chatting",
					"title": "UNSERE MÄDELS KOMMEN // WIR KOCHEN // 7VSWILD WATCHPARTY LETZTE FOLGE // SNOWTRIP TAG 8"
				}
			},
			{
				"id": "1705854681380-0",
				"message": {
					"timestamp": "1705854681379",
					"viewer": "6164",
					"gameName": "Just Chatting",
					"title": "UNSERE MÄDELS KOMMEN // WIR KOCHEN // 7VSWILD WATCHPARTY LETZTE FOLGE // SNOWTRIP TAG 8"
				}
			}
		]
	},
	"slive": {
		"badge": []
	}
}
```
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{
	"code": 401,
	"message": "Authorization has failed - invalid Bearer token"
}
```
{% endtab %}

{% tab title="404: Not Found " %}
```json
{
	"code": 404,
	"message": "User not found"
}
```
{% endtab %}
{% endtabs %}

## Erhalte alle Events aus einem Stream

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/me/live/events`

Wir bieten momentan Subs, Subbombs, Cheers, Raids und Follows an.

#### Query Parameters

| Name  | Type | Description                                                |
| ----- | ---- | ---------------------------------------------------------- |
| start | Int  | Zeitpunkt in UNIX (ms), ab welcher Daten ausgegeben werden |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"channel.follow": [
		{
			"user_id": "425845421",
			"user_login": "hells_nightmare_",
			"user_name": "hells_nightmare_",
			"broadcaster_user_id": "31021656",
			"broadcaster_user_login": "thejocraft_live",
			"broadcaster_user_name": "thejocraft_live",
			"followed_at": "2023-12-27T18:23:47.684805644Z"
		}
	],
	"channel.subscription.message": [
		{
			"user_id": "868431381",
			"user_login": "pyr0techniker2000",
			"user_name": "pyr0techniker2000",
			"broadcaster_user_id": "31021656",
			"broadcaster_user_login": "thejocraft_live",
			"broadcaster_user_name": "thejocraft_live",
			"message": {
				"text": "Hallo, Ich hoffe dir geht es gut und hattest schöne Feiertage",
				"emotes": null
			},
			"tier": "1000",
			"cumulative_months": 10,
			"streak_months": 0,
			"duration_months": 0
		}
	],
	"channel.subscription.gift": [
		{
			"user_id": "614249275",
			"user_login": "anzugspyjama",
			"user_name": "Anzugspyjama",
			"broadcaster_user_id": "31021656",
			"broadcaster_user_login": "thejocraft_live",
			"broadcaster_user_name": "thejocraft_live",
			"tier": "1000",
			"total": 1,
			"cumulative_total": 1,
			"is_anonymous": false
		}
	],
	"channel.cheer": [
		{
			"broadcaster_user_id": "31021656",
			"broadcaster_user_login": "thejocraft_live",
			"broadcaster_user_name": "thejocraft_live",
			"is_anonymous": false,
			"user_id": "277536600",
			"user_login": "mircorump",
			"user_name": "MircoRump",
			"message": "Cheer100  ja heute ist tatsechlich 25%. ein Sub kostet 2.99€",
			"bits": 100
		}
	],
	"channel.raid": [
		{
			"from_broadcaster_user_id": "781582718",
			"from_broadcaster_user_login": "pabu_master",
			"from_broadcaster_user_name": "Pabu_Master",
			"to_broadcaster_user_id": "31021656",
			"to_broadcaster_user_login": "thejocraft_live",
			"to_broadcaster_user_name": "thejocraft_live",
			"viewers": 1
		}
	]
}
```
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
