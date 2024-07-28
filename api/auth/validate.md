# Validate

Validiere einen Token, den du von slive erhalten hast.

## sliveApp API Token Validate

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/auth/validate`

Validiere einen Token

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"meta": {
		"context": "website",
		"plattform": "twitch"
	},
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
	"expiresIn": 85803,
	"expiresAt": "2023-12-26T20:02:48.682Z"
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
