# SS Wheels – Katalog

Übersichtsseite (im Stil von tutti.ch) für die Felgen und Fahrzeug-Occasionen von
**SS Wheels** ([@ss.wheels_felgenshop](https://www.instagram.com/ss.wheels_felgenshop/)).

Filterbar nach Zoll, Lochkreis, Fahrzeugmarke und Design – plus ein Bereich für die
Occasionen mit Verweis auf die jeweilige Instagram-Story.

## Live

Nach Aktivierung von GitHub Pages erreichbar unter:
`https://<user>.github.io/ss-wheels-katalog/`

## Aufbau

Alles steckt in **einer einzigen Datei** – `index.html`. Kein Build, kein Server,
keine Abhängigkeiten. Die Bilder sind direkt in die Datei eingebettet
(`const IMAGES = { … }`).

## Bestand pflegen

`index.html` öffnen und im `<script>`-Block ganz oben bearbeiten:

| Was | Wo |
|-----|-----|
| Felgen | Array `WHEELS` – ein `{ … }` pro Felge/Satz. Felder `price` (Zahl oder `null` = „Preis auf Anfrage"), `condition` (Zustand), `link` (Instagram-Post) und `fbLink` (Facebook-Marketplace-Inserat) sind alle optional – leer lassen, was nicht zutrifft. |
| Occasionen (Autos) | Array `CARS` |
| Kontakt / WhatsApp-Nummer | Objekt `SHOP` (`whatsapp: "41791234567"` eintragen → „Anfragen"-Button geht direkt zu WhatsApp; `facebook` verlinkt im Footer auf den Marketplace-Shop) |
| Bilder | Objekt `IMAGES` – Schlüssel = `img`-Feld des Inserats. Wert: `"data:image/jpeg;base64,…"` **oder** eine normale Bild-URL (`"https://…"`). Ohne Treffer wird eine Felgen-/Auto-Illustration gezeichnet. |

Ein Feld leer lassen (`""` bzw. `[]`), wenn eine Angabe fehlt – die Zeile wird
dann einfach nicht angezeigt.

Danach die Datei speichern und committen:

```bash
git add index.html
git commit -m "Bestand aktualisiert"
git push
```

GitHub Pages veröffentlicht die Änderung automatisch in ein bis zwei Minuten.

## Hinweis zu den Daten

Fotos und Beschreibungen stammen aus dem öffentlichen Instagram-Profil sowie dem
Facebook-Marketplace-Shop von SS Wheels (echte Preise und Zustand der aktiven
Inserate). Bei den Occasionen zeigt die Karte das Titelbild der Story-Highlight;
Jahrgang, Kilometer und Preis stehen in der jeweiligen Story bzw. auf Anfrage.
Alle Angaben ohne Gewähr.
