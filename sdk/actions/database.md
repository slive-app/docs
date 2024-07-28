# Database

```javascript
// Wert speichern
SLIVE.db.set(key, value)

// Wert abrufen
let value = await SLIVE.db.get(key)
```

Wenn du eine Variabel abspeichern möchtest, kannst du als `key` jeden Wert nehmen, den du möchtest. Auch die `value` wird so abgespeichert, wie du sie uns gibst. \
Alle Daten werden auf unserem Redis-Server abgespeichert.

{% hint style="warning" %}
Beachte, dass alle gespeicherten Keys nach 30 Tagen gelöscht werden, sollten diese nicht erneuert werden.
{% endhint %}

***

## Advanced

\
Beim Speichern und Abrufen hast du nur Zugriff auf die hintersten beiden Speicherebene.

<pre><code>database:userId:overlayId:<a data-footnote-ref href="#user-content-fn-1">moduleId:yourKey</a>
</code></pre>

{% hint style="info" %}
Wenn der User seine OverlayIDs resetet, gehen automatisch alle abgespeicherten Daten verloren.&#x20;
{% endhint %}

Wenn du eine Variabel eines anderen Moduls abspeichern oder erhalten willst, musst du einfach nur die ID des Moduls getrennt mit einem Doppelpunkt vor den Namen des Keys packen.

#### Beispiel:

Wir befinden uns im Modul mit der ID `g1`\
\- `key1` - Wir erhalten den Value des Keys `key1` für `g1`\
\- `g2:key1` - Wir erhalten den Value des Keys `key1` für das Modul `g2`

[^1]: Auf diese Bereiche kannst du zugreifen
