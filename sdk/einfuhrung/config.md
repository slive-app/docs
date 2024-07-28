# Config

Damit dein Modul von unserem System richtig erkannt wird, benötigt die SDK ein paar Informationen von dir. Führe die Funktion `SLIVE.config.set()` so früh es geht auf, da sonst die Verbindung zum Backend geschlossen wird.&#x20;

<pre class="language-javascript" data-line-numbers data-full-width="false"><code class="lang-javascript">SLIVE.config.set({
    id: "<a data-footnote-ref href="#user-content-fn-1">app.slive.sdk.test</a>",
    name: "<a data-footnote-ref href="#user-content-fn-2">Overlay Test</a>",
    width: <a data-footnote-ref href="#user-content-fn-3">1920</a>,
    height: <a data-footnote-ref href="#user-content-fn-4">1080</a>
})
</code></pre>

| Key    | Type   | Funktion                   |
| ------ | ------ | -------------------------- |
| id     | String | Identifier als Reverse-DNS |
| name   | String | Name deines Overlays       |
| width  | Int    | Breite in Pixel            |
| height | Int    | Höhe in Pixel              |

Die SDK nutzt diese Informationen, um z.b. dein Overlay an das Display vom Streamer anzupassen.

[^1]: Deine ID als Reverse-DNS

[^2]: Ein Name, der im Controller angezeigt werden kann

[^3]: Breite in Pixel

[^4]: Höhe in Pixel
