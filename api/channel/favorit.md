# Favorit

## Ändere deine Favoriten

<mark style="color:orange;">`PUT`</mark> `https://api.slive.app/channel/<channelId>/favs`

Wenn du diesen Endpoint aufrufst, switchst du den Wert in unserer Datenbank. Achte daher darauf, welche Informationen du in der Response erhältst.

#### Path Parameters

| Name                                        | Type   | Description |
| ------------------------------------------- | ------ | ----------- |
| channelId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

#### Request Body

| Name                                   | Type   | Description                                     |
| -------------------------------------- | ------ | ----------------------------------------------- |
| id<mark style="color:red;">\*</mark>   | String | ID des Moduls                                   |
| type<mark style="color:red;">\*</mark> | String | Typ des Moduls \[game, tool, background, event] |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"id": "app.slive.tool.clips",
	"type": "tool",
	"added": true,
	"removed": false,
	"favs": {
		"games": [
			"de.thejocraft.game.villager"
		],
		"events": [],
		"tools": [
			"app.slive.tool.default",
			"app.slive.tool.clips"
		],
		"backgrounds": []
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
	"message": "${body.type} not found"
}
```
{% endtab %}
{% endtabs %}
