# Website – Watchfaces & Apps (GitHub Pages)

Dieser Ordner ist die **lokale Kopie des öffentlichen GitHub-Repositorys `WatchFace`**
(Benutzer `HeAtsszeen`, Adresse `https://heatsszeen.github.io/WatchFace/`).
Alles hier ist öffentlich – **niemals** `keygen.html`, geheime Schlüssel oder Projektdateien hier ablegen.

## Aufbau

```
Website/
├── index.html            Übersicht aller Watchfaces und Apps (6 Sprachen), Impressum, Datenschutz
│                         + Weiterleitung alter My-Memories-Links (…/WatchFace/?id=…) nach mymemories/
├── mymemories/
│   └── index.html        Freischaltseite My Memories (3,49 €) – unveränderte Kopie der bisherigen Seite
├── worldchrono/
│   └── index.html        Freischaltseite World Chrono (1,99 €)
└── assets/
    ├── mymemories/       hero_de.jpg, hero_en.jpg
    └── worldchrono/      hero.jpg, icon.png
```

Adressen nach dem Hochladen:
- Übersicht: `https://heatsszeen.github.io/WatchFace/`
- My Memories: `https://heatsszeen.github.io/WatchFace/mymemories/?id=XXXX-XXXX`
  (die in der App eingebaute alte Adresse `…/WatchFace/?id=…` leitet automatisch hierher weiter)
- World Chrono: `https://heatsszeen.github.io/WatchFace/worldchrono/?id=XXXX-XXXX` (so in `License.mc` eingetragen)

## Hochladen (GitHub im Browser)

1. github.com → Repository `WatchFace` öffnen.
2. **Add file → Upload files** → den **Inhalt** dieses Ordners hineinziehen (`index.html`, die Ordner
   `mymemories`, `worldchrono`, `assets`; `README.md` darf mit). Vorhandene `index.html` wird ersetzt – das ist gewollt.
3. **Commit changes**.
4. Nach 1–2 Minuten testen:
   - `https://heatsszeen.github.io/WatchFace/` → Übersicht
   - `https://heatsszeen.github.io/WatchFace/?id=B602-D74A` → muss auf die My-Memories-Seite weiterleiten
   - `https://heatsszeen.github.io/WatchFace/worldchrono/?id=B602-D74A` → World-Chrono-Seite mit ID

> Pfade unterscheiden Groß-/Kleinschreibung (`/WatchFace/`, Ordner klein).

## Neue App hinzufügen

1. Ordner `<appname>/` anlegen (klein, ohne Leerzeichen) und `worldchrono/index.html` als Vorlage kopieren.
2. In der Kopie ändern: Titel/Namen (alle 6 Sprachen), Preis, `PAYPAL_ME` (Betrag), `APP_NAME`, Icon-Pfad,
   Datenschutz Punkt 7 (was die App auf der Uhr tut), Widerrufsformular (App-Name).
3. Bilder nach `assets/<appname>/`.
4. In `index.html` im Skript einen Eintrag in `APPS` ergänzen (Name, Preis, Texte, Bild, Store-Link).
5. In der App: `UNLOCK_URL = "https://heatsszeen.github.io/WatchFace/<appname>/"`.

## Store-Links eintragen

Sobald eine App im Connect IQ Store ist: in `index.html` bei `APPS` das Feld `store` mit dem Store-Link füllen.
Solange es leer ist, zeigt die Karte „Bald im Connect IQ Store“.

## Preise ändern

Freischaltseite: alle Preisangaben in den Texten und `PAYPAL_ME` (z. B. `.../1.99EUR`), dazu der Eintrag in `APPS` in `index.html`.
In der App: `PriceText` in den Sprachdateien (World Chrono: `tools/gen_strings.py`).
