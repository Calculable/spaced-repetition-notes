# Remote Push: Konzeptionell
📣

## Schritt 1: Token bekanntgeben

- Das App Token ist pro App-Gerät Kombination eindeutig
- Das Token kann sich mit der Zeit verändern, deshalb muss man bei jedem App-Start bei APNS das Token abfragen

![][image-1]

## Schritt 2: Push Nachricht senden

![][image-2]
(HTTP/2 Post Request)

## Rohdatei
push.drawio

## Details
Guter Einführungstalk: [https://developer.apple.com/wwdc20/10095][1]


## Zusammenfassung
- Apple's Push Server heissen...
- Welche Schritte sind nötig, bis eine Remote Push Notification beim Gerät ankommt




[1]:	https://developer.apple.com/wwdc20/10095

[image-1]:	assets/1.png
[image-2]:	assets/2.png

#learning unit#