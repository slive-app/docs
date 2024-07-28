# Tools

## Ändere deine Tools

<mark style="color:orange;">`PUT`</mark> `https://api.slive.app/channel/<channelId>/tools`

Setze das Tool fest, welches du über das Overlay anzeigen lassen kannst.\
Beim ändern lädt dein Overlay automatisch neu und zeigt deine Auswahl an.\
\
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

| Name                                 | Type   | Description  |
| ------------------------------------ | ------ | ------------ |
| id<mark style="color:red;">\*</mark> | String | ID des Tools |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"id": "app.slive.tool.chat",
	"selected_tools": [
		"app.slive.tool.chat"
	],
	"added": true,
	"removed": false
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
	"message": "Tool not found"
}
```
{% endtab %}
{% endtabs %}
