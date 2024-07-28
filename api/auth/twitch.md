# Twitch

Die Autorisierung ist momentan etwas kompliziert gehalten. Du benötigst derzeit die Client-Id von slive. Nur so kann derzeit durch den klassischen Auth-Flow von Twitch ein Code generiert werden.

## Twitch Autorisierung

<mark style="color:green;">`POST`</mark> `https://api.slive.app/auth/twitch`

Autorisiere dich mit deinem Twitch Account und erhalte einen Token zur API von sliveApp

#### Headers

| Name                                           | Type             | Description |
| ---------------------------------------------- | ---------------- | ----------- |
| Content-Type<mark style="color:red;">\*</mark> | application/json |             |

#### Request Body

| Name                                             | Type | Description                        |
| ------------------------------------------------ | ---- | ---------------------------------- |
| twitchAuthCode<mark style="color:red;">\*</mark> |      | Code-Type aus dem Twitch-Auth-Flow |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"token": "cV2tV8zgPSZcdhuba",
	"userId": "31021656",
	"userName": "thejocraft_live",
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
	],
	"expiresIn": 86400,
	"expiresAt": "2023-12-26T20:02:48.683Z"
}
```
{% endcode %}
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{
	"code": 401,
	"message": "Authorization with Twitch has failed - invalid auth code"
}
```
{% endtab %}
{% endtabs %}
