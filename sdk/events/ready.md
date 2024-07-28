# Ready

```javascript
SLIVE.on('ready', (data) => {})
```

Dieses Event wird ausgeführt, sobald die SDK erfolgreich eine Verbindung zu slive aufgebaut hat. Bitte lade deine Funktionen erst ab diesem Zeitpunkt. Sobald du soweit bist, dein Modul der Welt zu zeigen, rufe die Funktion `SLIVE.ready()` auf\
\
Das Event beinhaltet zudem Informationen zu der Verbindung und zum Streamer.
