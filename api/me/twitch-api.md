# Twitch API

{% hint style="danger" %}
Dieser Endpoint ist noch in aktiver Entwicklung und funktioniert nur unter bestimmten Umständen. Bitte warte, bis dieser Bereich offiziell veröffentlicht wird!
{% endhint %}

Wir bieten euch die Möglichkeit, das ihr die Twitch API ansteuern könnt. Nutzt dafür einfach diesen Endpoint und wir leiten alles 1:1 mit den Credentials des Streamers weiter.

## Helix API

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/me/twitch/api`

#### Query Parameters

| Name                                   | Type   | Description       |
| -------------------------------------- | ------ | ----------------- |
| path<mark style="color:red;">\*</mark> | String | Pfad zum Endpoint |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
Du erhältst die Informationen von der Twitch API
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{
	"code": 401,
	"message": "Authorization has failed - invalid Bearer token"
}
```
{% endtab %}

{% tab title="500: Internal Server Error " %}
```json
{
	"code": "Internal Server Error",
	"message": "Error while fetching data from Twitch API",
	"twitchError": {}
}
```
{% endtab %}
{% endtabs %}
