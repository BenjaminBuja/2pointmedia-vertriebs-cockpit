# 2Point Vertriebs-Cockpit

Eine einzige Datei: `public/index.html`. Kein Build-Schritt nötig.

## Veröffentlichen (Cloudflare)

Das Repo ist mit Cloudflare Workers verbunden. `wrangler.jsonc` sagt Cloudflare, dass der Ordner `public`
als Webseite veröffentlicht wird. Jede Änderung auf `main` wird automatisch veröffentlicht.

## Wo die Daten liegen

Alles wird im Browser auf dem jeweiligen Gerät gespeichert (`localStorage`, Schlüssel `cockpit-state` und `cockpit-log`).
Andere Geräte oder Browser sehen diese Daten nicht. Darum regelmässig im Reiter «Zahlen» auf **Daten sichern** klicken.
Mit **Daten laden** holst du eine Sicherung zurück, auch auf einem anderen Gerät.

## Später

- **HubSpot anbinden:** offene Angebote anzeigen und Angebote, auf die seit 3 oder mehr Tagen keine Antwort kam.
  Dafür braucht es einen kleinen Server-Teil, z.B. ein kleiner Cloudflare Worker im selben Projekt.
  Der HubSpot-Zugangsschlüssel gehört dort als geheime Umgebungsvariable hin, niemals in `public/index.html`,
  weil die Webseite öffentlich ist und jeder den Quelltext lesen kann.
  Die Seite selbst fragt dann nur die eigene Adresse ab (z.B. `/api/angebote`). Zusätzlich die Seite mit
  Cloudflare Access schützen, damit nur du die Zahlen siehst.
