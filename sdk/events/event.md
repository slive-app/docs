# Event

```javascript
SLIVE.on('event', (data) => {})
```

slive baut automatisch eine Verbindung zu Twitch's Eventsub auf und leitet alle verfügbaren Events an das Overlay weiter. Zur eigenen Sicherheit entfernen wir Informationen, die auf die Verbindung zurückzuführen sind oder ersetzen diese durch eigene.

Es ist zusätzlich möglich, nur auf einzelne Events zu hören. Das funktioniert, in dem du auf den Type hörst, der auf der offiziellen Seite von Twitch dokumentiert ist:

```javascript
SLIVE.on('channel.subscription.message', (data) => {})
```

{% hint style="warning" %}
Wir haben keinen Einfluss auf Änderungen seitens Twitch, versuchen aber Breaking Changes zu vermeiden.
{% endhint %}

{% hint style="info" %}
Mehr Informationen gibt es auf der offiziellen Seite von Twitch\
[https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/](https://dev.twitch.tv/docs/eventsub/eventsub-subscription-types/)
{% endhint %}

<pre class="language-json"><code class="lang-json">{
	"subscription": {
		"id": "<a data-footnote-ref href="#user-content-fn-1">valWdj9a2YJPLR2tACatmsd9Hy3FwKMnuDz7xmG9wRA</a>=",
		"type": "channel.subscription.message",
		"version": "1",
		"created_at": "2023-10-08T18:48:44.422343786Z"
	},
	"event": {
		"user_id": "131501829",
		"user_login": "tjc_bot",
		"user_name": "TJC_Bot",
		"broadcaster_user_id": "31021656",
		"broadcaster_user_login": "thejocraft_live",
		"broadcaster_user_name": "thejocraft_live",
		"message": {
			"text": "Wusstest du, dass man einen Netherstern mit einem Eimer Wasser fangen kann? Nein? Kein Wunder denn dieser Fakt wurde Ihnen präsentiert von: Google Bard.",
			"emotes": null
		},
		"tier": "1000",
		"cumulative_months": 56,
		"streak_months": 32,
		"duration_months": 0
	}
}
</code></pre>

[^1]: Wird von uns durch eine eigene ID ersetzt
