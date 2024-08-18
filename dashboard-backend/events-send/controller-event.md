# Controller Event

{% hint style="info" %}
Nur gültig für Origin-Typ **dashboard**
{% endhint %}

Hier senden wir die Information, dass der User mit einem Objekt auf der Website interagiert hat. Die Payload beinhaltet die Information, welches Modul angesprochen wurde und alle Informationen über das entsprechende Interaktions-Objekt.

<details>

<summary>Action Object</summary>

{% code fullWidth="true" %}
```json
{
    "ID": "PF2PB_CONTROLLER_EVENT",
    "DATA": {
        "module": {
            "id": "studio3_template"
        },
        "interaction": {
            "type": "button",
            "name": "Einschalten",
            "color": "danger",
            "id": "54I7A0U1n0j7F4Y"
        }
    }
}
```
{% endcode %}

</details>
