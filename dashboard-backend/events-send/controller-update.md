# Controller Update

{% hint style="info" %}
Nur gültig für Origin-Typ **overlay**
{% endhint %}

Das Overlay sendet zusammen mit seiner Modul-ID die Informationen, welche Informationen auf der Website angezeigt werden sollen.&#x20;

<details>

<summary>Action Object</summary>

<pre class="language-json" data-full-width="true"><code class="lang-json">
<strong>{
</strong>        "ID": "OF2PB_CONTROLLER_UPDATE",
        "DATA": {
            "module": {
                "id": "app.slive.event.tjcteam.diawars2",
                "name": "DiaWars2",
            },
            "controller": [{
                "type": "container",
                "name": "AreaChecker",
                "description": "Schalte die AreaChecker ein oder aus",
                "items": [{
                    "type": "button",
                    "name": "Einschalten",
                    "color": "danger",
                }]
            }]
        }
    }

</code></pre>

</details>
