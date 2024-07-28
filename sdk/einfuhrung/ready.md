# Ready?

Wenn du mit der Config fertig bist, muss die SDK nur noch wissen, dass du mit deinem Code bereit bist. Am einfachsten geht das mit diesem Code:

{% code lineNumbers="true" %}
```javascript
SLIVE.on('ready', (config) => {
    SLIVE.ready()
})
```
{% endcode %}

Was genau dieser Code macht, bröseln wir in den einzelnen Abschnitten auf.\
Wichtig ist nur, dass du mit dem laden deines Skriptes erst dann beginnst, sobald du das "ready"-Event von slive erhältst. Sobald du dann mit deinem Teil durch bist, rufst du die Funktion `SLIVE.ready()` auf. Ab diesem Zeitpunkt siehst du dein Modul im Browser oder in OBS und erhältst Events.&#x20;
