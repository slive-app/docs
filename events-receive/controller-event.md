# Controller Event

{% hint style="info" %}
Nur gültig für Origin-Typ **overlay**
{% endhint %}

Hier erhält das Overlay die Information, dass der User auf der Website mit einem Controller-Element interagiert hat. Im `.interaction`-Objekt sind immer `.id` und `.value` zu finden. Die anderen Werte werden beim setzen der Controller-Settings vom Entwickler selbst festgelegt.

<details>

<summary>Event Object</summary>

{% code fullWidth="true" %}
```json
{
    "ID": "PB2OF_CONTROLLER_EVENT",
    "CODE": 200,
    "MESSAGE": "Controller Event",
    "DATA": {
        "module": {
            "id": "app.slive.event.tjcteam.diawars2"
        },
        "interaction": {
            "type": "button",
            "name": "Einschalten",
            "color": "danger",
            "value": "",
            "id": "54I7A0U1n0j7F4Y"
        }
    }
}
```
{% endcode %}

</details>
