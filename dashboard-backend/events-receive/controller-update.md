# Controller Update

{% hint style="info" %}
Nur gültig für Origin-Typ **dashboard**
{% endhint %}

In diesem Event erhält das Dashboard eine Liste mit allen von Modulen aktivierten Controllern. Dieses wird auf der Website dafür genutzt, den Controller zu aktivieren und die einzelnen Container zu laden.\
\
Dieses Event wird nur gefeuert, wenn mindestens ein Overlay aktiviert und ein Modul Einstellungen für den Controller gesetzt hat. Sobald kein Overlay mehr aktiv ist, wird dieses Event ohne ein Data-Objekt gefeuert.

<details>

<summary>Event Object</summary>

{% code fullWidth="true" %}
````json
```json
{
    "ID": "PB2PF_CONTROLLER_UPDATE",
    "CODE": 200,
    "MESSAGE": "Controller Update",
    "DATA": {
        "studio3_template": {
            "module": {
                "id": "app.slive.event.tjcteam.diawars2",
                "name": "DiaWars2"
            },
            "controller": [{
                "type": "container",
                "name": "AreaChecker",
                "description": "Schalte die AreaChecker ein oder aus",
                "items": [{
                    "type": "button",
                    "name": "Einschalten",
                    "color": "danger",
                    "id": "54I7A0U1n0j7F4Y"
                }]
            }]
        }
    }
}
```
````
{% endcode %}

</details>
