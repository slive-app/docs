# Overlay

## Generiere neue Overlay Tokens

<mark style="color:green;">`POST`</mark> `https://api.slive.app/me/renew/overlays`

Du erhältst 4 Tokens, die du zum Verbinden mit dem Backend benötigst. Jeder Overlaytoken beinhaltet Zugang zu unterschiedlichen Bereichen.

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"overlays": {
		"game": "GXXXXXXXX",
		"tool": "TXXXXXXXX",
		"background": "BXXXXXXXX",
		"event": "EXXXXXXXX"
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
