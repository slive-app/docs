# Backgrounds

## Ändere deinen Background

<mark style="color:orange;">`PUT`</mark> `https://api.slive.app/channel/<channelId>/backgrounds`

Setze den Hintergrund, welches du über das Overlay anzeigen lassen kannst.\
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

| Name                                 | Type   | Description        |
| ------------------------------------ | ------ | ------------------ |
| id<mark style="color:red;">\*</mark> | String | ID des Backgrounds |

{% tabs %}
{% tab title="200: OK " %}
```json
{
	"id": "app.slive.background.default"
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
	"message": "Background not found"
}
```
{% endtab %}
{% endtabs %}
