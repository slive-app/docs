# Backgrounds

Besorgt euch eine Liste von allen Backgrounds oder einen einzelnen Eintrag mit mehr Infos

## Erhalte eine Liste mit allen verfügbaren Backgrounds

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/backgrounds`

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
	"backgrounds": [
		{
			"id": "app.slive.background.default",
			"name": "Default",
			"tier": 0,
			"shortDescription": "Default",
			"label": {
				"name": "New",
				"color": "#971ad6"
			}
		},
		{
			"id": "de.thejocraft.background.chat",
			"name": "TJC Chat",
			"tier": 1,
			"shortDescription": "Chat-Hintergrund",
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

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/backgrounds/<backgroundId>`

Dieser Eintrag wird generiert mit einem vorherigen Check deiner Zugriffe.

#### Path Parameters

| Name                                           | Type   | Description |
| ---------------------------------------------- | ------ | ----------- |
| backgroundId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "de.thejocraft.background.chat",
	"name": "TJC Chat",
	"type": "background",
	"tier": 1,
	"shortDescription": "Chat-Hintergrund",
	"description": "Lasse den Chat im Hintergrund deines Streams fliegen.",
	"label": {
		"name": "Updated",
		"color": "#d61a97"
	},
	"updatedAt": "2023-12-10T00:04:17.000Z"
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
