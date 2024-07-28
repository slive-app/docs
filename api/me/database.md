# Database

{% hint style="warning" %}
Nur möglich, wenn der Token von einem Overlay generiert wurde
{% endhint %}

slive bietet Entwicklern die Möglichkeit, Daten abzuspeichern. Diese werden jedem Nutzer zugeordnet.

## Speichere einen Wert in die Datenbank

<mark style="color:purple;">`PATCH`</mark> `https://api.slive.app/me/database`

Setze eine Variabel in die Datenbank von slive. Diese Variabeln werden für jeden OverlayType und User einzelnd aufbewart. Um eine Variabel für das derzeitige Modul zu setzen, muss man nur den Namen des Keys einsetzen. Möchte man stattdessen eine Variabel eines anderen Moduls ändern, muss diese ID vor dem Namen des Keys getrennt mit einem `:` geschrieben werden.

Beispiel: \
Wir befinden uns im Modul mit der ID `g1`\
\- `key1` - Wir erhalten den Value des Keys `key1` für `g1`\
\- `g2:key1` - Wir erhalten den Value des Keys `key1` für das Modul `g2`

#### Headers

| Name                                            | Type             | Description |
| ----------------------------------------------- | ---------------- | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer           |             |
| Content-Type<mark style="color:red;">\*</mark>  | application/json |             |

#### Request Body

| Name                                    | Type   | Description                                     |
| --------------------------------------- | ------ | ----------------------------------------------- |
| id<mark style="color:red;">\*</mark>    | String | ID des eigenen Moduls                           |
| key<mark style="color:red;">\*</mark>   | String | Key, welches abgespeichert werden soll          |
| value<mark style="color:red;">\*</mark> | custom | Hier kannst du alles abspeichern, was du willst |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "g1",
	"key": "key1",
	"value": "Ein super Test"
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

## Erhalte einen Eintrag aus der Datenbank

<mark style="color:blue;">`GET`</mark> `https://api.slive.app/me/database`

Erhalte eine Variabel aus der Datenbank von slive. Um eine Variabel erhalten zu können, muss diese vorher mit dem POST gesetzt werden. Um eine Variabel für das derzeitige Modul zu erhalten, muss man nur den Namen des Keys einsetzen. Möchte man stattdessen eine Variabel eines anderen Moduls erhalten, muss diese ID vor dem Namen des Keys getrennt mit einem `:` geschrieben werden.

Beispiel: \
Wir befinden uns im Modul mit der ID `g1`\
\- `key1` - Wir erhalten den Value des Keys `key1` für `g1`\
\- `g2:key1` - Wir erhalten den Value des Keys `key1` für das Modul `g2`

#### Query Parameters

| Name                                  | Type   | Description                        |
| ------------------------------------- | ------ | ---------------------------------- |
| key<mark style="color:red;">\*</mark> | String | Key, welcher abgefragt werden soll |
| id<mark style="color:red;">\*</mark>  | String | ID des eigenen Moduls              |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | Bearer |             |

{% tabs %}
{% tab title="200: OK " %}
{% code fullWidth="false" %}
```json
{
	"id": "g1",
	"key": "key1",
	"value": "Ein super Test"
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
