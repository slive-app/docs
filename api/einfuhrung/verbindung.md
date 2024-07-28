# Verbindung

Unsere API hat das Ziel, dass man sich ohne große Probleme orientieren kann. \
Du kannst die Verbindung in deinem gewohnten Dev-Umfeld aufbauen. Nutze dafür folgende URL:

{% tabs %}
{% tab title="Stable" %}
> https://api.slive.app
{% endtab %}

{% tab title="Beta" %}
> https://apibeta.slive.app

{% hint style="warning" %}
Tokens sind abhängig von der Produktions-Umgebung. Wenn du einen Token von [slive.app](https://slive.app) verwendest, wird dieser **nicht** funktionieren. Generiere dir hierfür einen Token von [beta.slive.app.](https://beta.slive.app)
{% endhint %}
{% endtab %}
{% endtabs %}

### Token Context

Je nach Ursprung des Tokens erhält man Zugriff auf mehr oder weniger Bereiche der API. Du kannst einen Token immer Validieren und so herausfinden, woher dieser stammt.

<table data-full-width="false"><thead><tr><th width="185">Type</th><th>Generierung</th><th>Gültigkeit</th></tr></thead><tbody><tr><td>Website</td><td>Durch unseren klassischen Auth-Flow</td><td>24 Stunden</td></tr><tr><td>Overlay</td><td>Durch das Laden des Overlays</td><td>Nur solange das Overlay aktiv ist</td></tr></tbody></table>

### Token Plattform

Uns ist wichtig, dass wir in Zukunft auch weitere Plattformen wie YouTube unterstützen. Um die Tokens auch hier unterscheiden zu können, sind diese durch die Plattformen abhängig gültig.\
Unterstützt wird aktuell:

| Plattform | API Version | Eingeführt |
| --------- | ----------- | ---------- |
| Twitch    | >1.0        | 05.2023    |
