# Ping Pong

Neben dem regulären Ping Pong, welches von den meisten Websocket-Libaries abgedeckt wird, benötigen wir eine zusätzliche Info.

Wir senden alle 5 Minuten ein Event, das so aussieht:

{% content-ref url="../../overlay-backend/events-receive/ping.md" %}
[ping.md](../../overlay-backend/events-receive/ping.md)
{% endcontent-ref %}

Du hast mit dem Erhalt 10 Sekunden Zeit, auf diese Anfrage zu antworten. Sende uns dafür folgende Antwort:

{% code lineNumbers="true" %}
```json
{
    "ID": "AF2PB_PONG",
    "DATA": {}
}
```
{% endcode %}

Sollten wir in dieser Zeit keine Antwort erhalten haben, schließen wir die Verbindung und du musst dich erneut mit dem Backend verbinden.
