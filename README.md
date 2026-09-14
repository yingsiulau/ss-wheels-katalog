# SS Wheels – Katalog

Übersichtsseite (im Stil von tutti.ch) für die Felgen und Fahrzeug-Occasionen von
**SS Wheels** ([@ss.wheels_felgenshop](https://www.instagram.com/ss.wheels_felgenshop/)).

Filterbar nach Zoll, Lochkreis, Fahrzeugmarke, Design und Zustand – mit drei
Bereichen: **Felgen**, **Occasionen** (Autos) und **Einzelteile** (Ersatzteile/Zubehör).

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
| Felgen | Array `WHEELS` – ein `{ … }` pro Felge/Satz. Felder `price` (Zahl oder `null` = „Preis auf Anfrage"), `condition` (Zustand), `link` (Instagram-Post), `fbLink` (Facebook-Marketplace) und `tuttiLink` (Tutti.ch) sind alle optional – leer lassen, was nicht zutrifft. |
| Occasionen (Autos) | Array `CARS`. Bei einer echten Inserat-Occasion zusätzlich `price`, `year`, `km`, `mfk`, `condition` setzen – sonst gilt sie als reine Instagram-Story-Referenz. |
| Einzelteile | Array `PARTS` – Ersatzteile/Zubehör, gleiches Schema wie Felgen (ohne Grösse/Lochkreis). |
| Kontakt / WhatsApp-Nummer | Objekt `SHOP` (`whatsapp: "41791234567"` eintragen → „Anfragen"-Button geht direkt zu WhatsApp; `facebook`/`tutti` verlinken im Footer auf die jeweiligen Shops) |
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

Fotos und Beschreibungen stammen aus dem öffentlichen Instagram-Profil sowie den
Facebook-Marketplace- und Tutti.ch-Shops von SS Wheels (echte Preise und Zustand
der aktiven Inserate). Bei den Story-Occasionen zeigt die Karte nur das Titelbild
der Instagram-Story; Jahrgang, Kilometer und Preis stehen dort bzw. auf Anfrage.
Alle Angaben ohne Gewähr.
