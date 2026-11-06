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
