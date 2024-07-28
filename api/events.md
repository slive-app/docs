# Events

Besorgt euch eine Liste von allen Events oder einen einzelnen Eintrag mit mehr Infos

## Erhalte eine Liste mit allen verfügbaren Events

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/events`

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
			"id": "app.slive.event.default",
			"name": "Default",
			"tier": 0,
			"shortDescription": "Default",
			"label": {
				"name": "New",
				"color": "#971ad6"
			}
		},
		{
			"id": "de.thejocraft.event.diawars",
			"name": "TJC Diawars",
			"tier": 1,
			"shortDescription": "Overlay für das Projekt Diawars",
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

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/events/<eventId>`

Dieser Eintrag wird generiert mit einem vorherigen Check deiner Zugriffe.

#### Path Parameters

| Name                                      | Type   | Description |
| ----------------------------------------- | ------ | ----------- |
| eventId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "de.thejocraft.event.diawars",
	"name": "TJC Diawars",
	"type": "event",
	"tier": 1,
	"shortDescription": "Overlay für das Projekt Diawars",
	"description": "Das große Overlay für das große Projekt.",
	"label": {
		"name": "Updated",
		"color": "#d61a97"
	},
	"updatedAt": "2023-09-23T15:09:01.000Z"
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
