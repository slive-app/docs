# Events

## Ändere dein Event

<mark style="color:orange;">`PUT`</mark> `https://api.slive.app/channel/<channelId>/events`

Setze das Event fest, welches du über das Overlay anzeigen lassen kannst.\
Beim ändern lädt dein Overlay automatisch neu und zeigt deine Auswahl an.

#### Path Parameters

| Name                                        | Type   | Description |
| ------------------------------------------- | ------ | ----------- |
| channelId<mark style="color:red;">\*</mark> | String |             |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

#### Request Body

| Name                                 | Type   | Description   |
| ------------------------------------ | ------ | ------------- |
| id<mark style="color:red;">\*</mark> | String | ID des Events |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"id": "app.slive.event.default"
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
	"message": "Event not found"
}
```
{% endtab %}
{% endtabs %}
