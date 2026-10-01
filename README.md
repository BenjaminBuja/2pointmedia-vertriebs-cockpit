# 2Point Vertriebs-Cockpit

Eine einzige Datei: `index.html`. Kein Build-Schritt nötig.

## Veröffentlichen (Cloudflare Pages)

Repo mit Cloudflare Pages verbinden, Build-Befehl leer lassen, Ausgabeordner `/`.

## Wo die Daten liegen

Alles wird im Browser auf dem jeweiligen Gerät gespeichert (`localStorage`, Schlüssel `cockpit-state` und `cockpit-log`).
Andere Geräte oder Browser sehen diese Daten nicht. Darum regelmässig im Reiter «Zahlen» auf **Daten sichern** klicken.
Mit **Daten laden** holst du eine Sicherung zurück, auch auf einem anderen Gerät.

## Später

- **HubSpot anbinden:** offene Angebote anzeigen und Angebote, auf die seit 3 oder mehr Tagen keine Antwort kam.
  Dafür braucht es einen kleinen Server-Teil, z.B. Cloudflare Pages Functions (`/functions/api/...`).
  Der HubSpot-Zugangsschlüssel gehört dort als geheime Umgebungsvariable hin, niemals in `index.html`,
  weil die Webseite öffentlich ist und jeder den Quelltext lesen kann.
  Die Seite selbst fragt dann nur die eigene Adresse ab (z.B. `/api/angebote`). Zusätzlich die Seite mit
  Cloudflare Access schützen, damit nur du die Zahlen siehst.
