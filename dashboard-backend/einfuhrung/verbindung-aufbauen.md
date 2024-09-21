# Verbindung aufbauen

Wir nutzen zur Kommunikation Websockets. Du kannst dich mit einem beliebigen Auth-Token mit dem Server verbinden.

Du kannst die Verbindung in deinem gewohnten Dev-Umfeld aufbauen. Nutze dafür folgende URL:

{% tabs %}
{% tab title="Stable" %}
> wss://ws.slive.app/?version=[**1**](#user-content-fn-1)[^1]\&token=[**TOKEN**](#user-content-fn-2)[^2]\&origin=[**ORIGIN**](#user-content-fn-3)[^3]
{% endtab %}

{% tab title="Beta" %}
> wss://ws.slive.app/beta?version=[**1**](#user-content-fn-4)[^4]\&token=[**TOKEN**](#user-content-fn-5)[^5]\&origin=[**ORIGIN**](#user-content-fn-6)[^6]

{% hint style="warning" %}
Tokens sind abhängig von der Produktions-Umgebung. Wenn du einen Token von [slive.app](https://slive.app) verwendest, wird dieser **nicht** funktionieren. Generiere dir hierfür einen Token von [beta.slive.app.](https://beta.slive.app)
{% endhint %}
{% endtab %}
{% endtabs %}

### Origin Types

Damit das Backend weiß, welche Partei welche Rolle hat, muss ein origin angegeben werden.

<table data-full-width="false"><thead><tr><th width="168">Type</th><th>Aufgabe</th></tr></thead><tbody><tr><td>dashboard</td><td>Erhält Blöcke mit Einstellungsmöglichkeiten</td></tr><tr><td>overlay</td><td>Sendet Informationen des Overlays</td></tr></tbody></table>



Um unnötigen Traffic zu vermeiden, überprüfen wir während dem Handshake die Gültigkeit des Tokens.  Sollte die Anfrage fehlschlagen, erhältst du im Header zusätzliche Informationen.&#x20;

Nach der erfolgreichen Verbindung bekommst du von uns folgende Info:

<details>

<summary>Authorization Success</summary>

{% code lineNumbers="true" %}
```json
{
    "ID": "PB2AF_AUTHORIZE_SUCCESS",
    "CODE": 200,
    "MESSAGE": "Connection authorized",
    "DATA": {}
}
```
{% endcode %}

</details>

[^1]: Aktuell ist nur Version 1 verfügbar

[^2]: Du erhältst Tokens entweder in einem Cookie auf der Website oder nach einer erfolgreichen Verbindung mit dem Overlay Backend

[^3]: Wird weiter unten erklärt

[^4]: Aktuell ist nur Version 1 verfügbar

[^5]: Gebe hier deinen Token ein, den du auf unserer [Website](https://beta.slive.app) erhältst.

[^6]: Wird weiter unten erklärt
