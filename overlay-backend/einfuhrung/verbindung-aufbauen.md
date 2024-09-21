# Verbindung aufbauen

Wir nutzen zur Kommunikation Websockets. Je nach Art deines Tokens (pro Account 4) erhälst du verschiedene Informationen bei der initialen Kommunikation.

Du kannst die Verbindung in deinem gewohnten Dev-Umfeld aufbauen. Nutze dafür folgende URL:

{% tabs %}
{% tab title="Stable" %}
> wss://ws.slive.app/?version=[**1**](#user-content-fn-1)[^1]\&token=[**TOKEN**](#user-content-fn-2)[^2]
{% endtab %}

{% tab title="Beta" %}
> wss://ws.slive.app/beta?version=[**1**](#user-content-fn-3)[^3]\&token=[**TOKEN**](#user-content-fn-4)[^4]

{% hint style="warning" %}
Tokens sind abhängig von der Produktions-Umgebung. Wenn du einen Token von [slive.app](https://slive.app) verwendest, wird dieser **nicht** funktionieren. Generiere dir hierfür einen Token von [beta.slive.app.](https://beta.slive.app)
{% endhint %}
{% endtab %}
{% endtabs %}

### Token Types

Pro Account generiert slive 4 verschiedene Tokens. Diese beinhalten verschiedene Overlays die der User einstellen kann. Diese sind:

<table data-full-width="false"><thead><tr><th width="168">Type</th><th width="87.33333333333331">Präfix</th><th>Limitierung</th></tr></thead><tbody><tr><td>Games</td><td>G</td><td>Ein Spiel max. wählbar</td></tr><tr><td>Tools</td><td>T</td><td>-</td></tr><tr><td>Backgrounds</td><td>B</td><td>Ein Hintergrund max. wählbar</td></tr><tr><td>Events</td><td>E</td><td>Nur für ausgewählte User</td></tr></tbody></table>



Um unnötigen Traffic zu vermeiden, überprüfen wir während dem Handshake die Gültigkeit des Tokens.  Sollte die Anfrage fehlschlagen, erhältst du im Header zusätzliche Informationen.&#x20;

Nach der erfolgreichen Verbindung bekommst du von uns folgende Info:

<details>

<summary>Authorization Success</summary>

{% code lineNumbers="true" %}
```json
{
    "ID": "OB2OF_AUTHORIZE_SUCCESS",
    "CODE": 200,
    "MESSAGE": "Connection authorized",
    "DATA": {}
}
```
{% endcode %}

</details>

[^1]: Aktuell ist nur Version 1 verfügbar

[^2]: Gebe hier deinen Token ein, den du auf unserer [Website](https://slive.app) erhältst.

[^3]: Aktuell ist nur Version 1 verfügbar

[^4]: Gebe hier deinen Token ein, den du auf unserer [Website](https://beta.slive.app) erhältst.
