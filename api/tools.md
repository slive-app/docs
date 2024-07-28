# Tools

Besorgt euch eine Liste von allen Tools oder einen einzelnen Eintrag mit mehr Infos

## Erhalte eine Liste mit allen verfügbaren Tools

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/tools`

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
	"tools": [
		{
			"id": "app.slive.tool.default",
			"name": "Default",
			"tier": 0,
			"shortDescription": "Default",
			"label": {
				"name": "New",
				"color": "#971ad6"
			}
		},
		{
			"id": "de.thejocraft.tool.raid",
			"name": "TJC Raidscreen",
			"tier": 1,
			"shortDescription": "Raidscreen für das Ende des Streams",
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

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/tools/<toolId>`

Dieser Eintrag wird generiert mit einem vorherigen Check deiner Zugriffe.

#### Path Parameters

| Name                                     | Type   | Description |
| ---------------------------------------- | ------ | ----------- |
| toolId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "de.thejocraft.tool.raid",
	"name": "TJC Raid",
	"type": "tool",
	"tier": 1,
	"shortDescription": "Raidscreen für das Ende des Streams",
	"description": "Zeigt eine Übersicht aller Ereignisse deines Streams während dem Raid an.",
	"label": {
		"name": "Updated",
		"color": "#d61a97"
	},
	"updatedAt": "2023-09-23T16:35:06.000Z"
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
