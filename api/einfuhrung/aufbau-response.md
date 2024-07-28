# Aufbau Response

## Startseite der API

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/`

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"meta": {
		"requestTime": "2023-12-25T19:07:22.174Z",
		"path": "/",
		"apiVersion": 1,
		"note": "The API is still in development. Please report any bugs to our Discord server.",
		"urls": {
			"docs": "https://docs.slive.app/api/v1/",
			"discord": "https://discord.gg/SmppCS8T95",
			"twitch": "https://dev.twitch.tv/status"
		}
	},
	"data": {
		"message": "Welcome to the official API of slive.app! 🎉 Before you start, it's best to read through the documentation first (which doesn't exist yet lol TDL)"
	}
}
```
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{
	"meta": {
		"requestTime": "2023-12-25T18:54:00.671Z",
		"path": "/",
		"apiVersion": 1,
		"note": "The API is still in development. Please report any bugs to our Discord server.",
		"urls": {
			"docs": "https://docs.slive.app/api/v1/",
			"discord": "https://discord.gg/SmppCS8T95",
			"twitch": "https://dev.twitch.tv/status"
		}
	},
	"error": {
		"code": 401,
		"message": "Authorization has failed - no Bearer token provided"
	}
}
```
{% endtab %}
{% endtabs %}

In jeder Antwort gibt es 2 Objekte, mit denen du (hoffentlich) etwas anfangen kannst.\
`obj.data` und `obj.error` können niemals gleichzeitig existieren!

<details>

<summary>obj.meta</summary>

Hier findest du Informationen über deine Anfrage. Es ist immer nützlich, auf `obj.meta.note` zu achten, da wir darüber Änderungen ankündigen.

```json
{
	"requestTime": "2023-12-25T18:54:00.671Z",
	"path": "/",
	"apiVersion": 1,
	"note": "The API is still in development. Please report any bugs to our Discord server.",
	"urls": {
		"docs": "https://docs.slive.app/api/v1/",
		"discord": "https://discord.gg/SmppCS8T95",
		"twitch": "https://dev.twitch.tv/status"
	}
}
```

</details>

<details>

<summary>obj.data</summary>

Wenn die Anfrage erfolgreich war, bekommst du über dieses Objekt deine angefragten Informationen.\
Die Daten unterscheiden sich je nach Anfrage.

</details>

<details>

<summary>obj.error</summary>

Dieses Objekt erscheint nur, wenn es einen Fehler bei deiner Anfrage gab. Unter `obj.error.message` erhältst du mehr Informationen. Diese können auch an den User weitergeleitet werden. \
`obj.error.data` hingegen gibt Informationen an, die für Entwickler wichtig sind. Auch für uns. Solltest du also einen Fehler entdecken, der tatsächlich von uns aus kommt, kannst du diese Information gerne über Discord weiterleiten.

</details>



{% hint style="info" %}
Im weiteren Verlauf der Dokumentation werden wir uns hauptsächlich auf `obj.data` konzentrieren und die Metadaten weglassen. **Bitte achtet unbedingt darauf!**
{% endhint %}
