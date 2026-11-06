# IPTV-XY-Releases

Hier liegen die fertigen Versionen von IPTV-XY (unter **Releases**). Der Quellcode ist in einem privaten Repo.

- Neueste APK: https://github.com/Pelzixx/IPTV-XY-Releases/releases/latest/download/iptv-xy.apk
- Downloader-Code: **6420457**

## Mitteilung und QR-Code auf der Startseite (`news.json`)

Die App liest `news.json` (höchstens alle 30 Minuten) und zeigt den Inhalt in der Info-Zeile der Startseite.
Leere Felder werden nicht angezeigt; sind alle leer, bleibt die Zeile bei der Mitteilung leer.

| Feld | Bedeutung |
|---|---|
| `title` | Überschrift der Mitteilung |
| `text` | Text der Mitteilung (bis 4 Zeilen) |
| `image` | Bild-Adresse (https://…, Querformat), optional |
| `qr` | Link, der als QR-Code angezeigt wird, z. B. `https://matrix.to/#/#raum:server` |
| `qrLabel` | Text neben dem QR-Code, z. B. „Support im Element-Chat“ |

Ändern: Datei auf GitHub öffnen, Stift-Symbol, Text ändern, „Commit changes“.

## sports.json – Top-Spiele im Sport-Guide

Diese Spiele erscheinen in der App oben auf der Sport-Seite (mit „TOP“ markiert), zusätzlich zu den Sportsendungen,
die automatisch aus dem TV-Programm erkannt werden. Sender werden über den Namen gefunden (z. B. „Sky Sport Bundesliga 1“
passt auch zu „DE| Sky Sport Bundesliga 1 HD“).

```json
{
  "events": [
    {
      "sport": "football",
      "league": "Bundesliga",
      "title": "FC Bayern – Borussia Dortmund",
      "home": "FC Bayern",
      "away": "Borussia Dortmund",
      "start": "2026-11-08T18:30:00+01:00",
      "end": "2026-11-08T20:30:00+01:00",
      "channels": ["Sky Sport Bundesliga 1", "Sky Sport Top Event"],
      "text": "Topspiel des Spieltags"
    }
  ]
}
```

- `sport`: football, basketball, motorsport, tennis, eishockey, nfl, boxen/ufc – alles andere landet unter „Weitere Sportarten“.
- `end` ist optional (sonst 2 Stunden nach Beginn). Vergangene Spiele werden automatisch ausgeblendet.
- `home`/`away` sind optional, damit werden Live-Spielstände zugeordnet.
