# Installieren

Naja, vom klassischen "installieren" kann man hier nicht sprechen. Aber ihr könnt stattdessen ganz einfach die aktuelle Version unserer SDK in euer Projekt einbinden:

{% tabs %}
{% tab title="Stable" %}
{% hint style="danger" %}
Diese Version wurde noch nicht veröffentlicht!
{% endhint %}

<pre class="language-html"><code class="lang-html"><strong>&#x3C;script defer src="https://cdn.jsdelivr.net/gh/slive-app/sdk@v1.1/_sliveBundle.js">&#x3C;/script>
</strong></code></pre>
{% endtab %}

{% tab title="Dev" %}
Wir veröffentlichen immer mal wieder Zwischenversionen der SDK, bevor diese als Stable gilt. Diese findest du auf unserer [Release-Seite](https://github.com/slive-app/sdk/releases) auf Github.

Wenn ein Snapshot vorhanden ist, musst du die jeweilige Nummer in der URL eintragen.

{% hint style="warning" %}
Snapshot-Releases werden entfernt, sobald die dafür vorgesehene Stable-Version veröffentlicht wurde.
{% endhint %}

<pre class="language-html"><code class="lang-html"><strong>&#x3C;script defer scr="https://cdn.jsdelivr.net/gh/slive-app/sdk@<a data-footnote-ref href="#user-content-fn-1">v1.1</a>/_sliveBundle.js">&#x3C;/script>
</strong></code></pre>
{% endtab %}
{% endtabs %}

Starte dann deinen Webserver (z.b. [LiveServer](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) oder [XAMPP](https://www.apachefriends.org/de/index.html)) und rufe deine Website auf.\
Du wirst von der SDK nach einem Overlaytoken gefragt, welchen du in die Alertbox eingeben musst. Du kannst diese Meldung entgehen, indem du in der URL die Query `?token=TOKEN` anhängst.

{% hint style="warning" %}
Wenn du eine Snapshot-Version nutzt, benötigst du einen Token von [beta.slive.app](https://beta.slive.app)
{% endhint %}

Du kannst jetzt in deinen JS-Dateien auf das SLIVE-Objekt zugreifen.

[^1]: Füge hier die Snapshot-Nummer ein
