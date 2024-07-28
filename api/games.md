# Games

Besorgt euch eine Liste von allen Games oder einen einzelnen Eintrag mit mehr Infos

## Erhalte eine Liste mit allen verfügbaren Games

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/games`

Diese Liste wird generiert mit einem vorherigen Check deiner Zugriffe.

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"games": [
		{
			"id": "app.slive.game.default",
			"name": "Default",
			"tier": 0,
			"shortDescription": "Default",
			"label": {
				"name": "New",
				"color": "#971ad6"
			}
		},
		{
			"id": "de.thejocraft.game.villager",
			"name": "TJC Villager",
			"tier": 1,
			"shortDescription": "Villager Game mit 2 Teams",
			"label": {
				"name": "Updated",
				"color": "#d61a97"
			}
		}
	]
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

## Erhalte einen einzelnen Eintrag

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/games/<gameId>`

Dieser Eintrag wird generiert mit einem vorherigen Check deiner Zugriffe.

#### Path Parameters

| Name                                     | Type   | Description |
| ---------------------------------------- | ------ | ----------- |
| gameId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "de.thejocraft.game.villager",
	"name": "TJC Villager",
	"type": "game",
	"tier": 1,
	"shortDescription": "Villager Game mit 2 Teams",
	"description": "Subs und Follower müssen gegeneinander Emeralds sammeln.",
	"label": {
		"name": "Updated",
		"color": "#d61a97"
	},
	"updatedAt": "2023-09-21T14:54:23.000Z"
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

{% tab title="404: Not Found " %}
```javascript
{
	"code": 404,
	"message": "No data found in database"
}
```
{% endtab %}
{% endtabs %}
