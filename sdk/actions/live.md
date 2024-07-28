# Live

Unter diesem Punkt erhaltet ihr Zugriff auf alle Events, die während des aktuellen Streams eingegangen sind.

{% hint style="warning" %}
sliveApp speichert pro Event-Kategorie nur die neusten 1000 Ereignisse ab.
{% endhint %}

{% hint style="info" %}
Die eingetragenen Werte stammen aus den Eventsubs von Twitch. Für mehr Informationen lohnt es sich, in die offizielle Dokumentation zu schauen: [https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/](https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/)
{% endhint %}

## Alle Events

Wenn ihr diese Fumktion aufruft, gibt euch slive alle Daten des aktuellen Streams geordnet nach Eingang des Events. Der erste Eintrag pro Kategorie ist der neuste.

```javascript
const events = SLIVE.live.events()
```

Für mehr Informationen, schaut euch die Dokumentation in unserer API-Sektion an:

{% content-ref url="../../api/me/live.md" %}
[live.md](../../api/me/live.md)
{% endcontent-ref %}
