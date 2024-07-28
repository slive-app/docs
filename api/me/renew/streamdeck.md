# Streamdeck

## Generiere einen neuen Streamdeck Token

<mark style="color:green;">`POST`</mark> `https://api.slive.app/me/renew/streamdeck`

Dieser Token wird für die Verbindung mit deinem Streamdeck benötigt. Du erhältst Zugriff auf das Overlay und kannst so Module steuern.

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"streamdeck": {
		"token": "sliveapp_sd_XXXXXXXX"
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
