# Sirikit - Intent Donation
👏

##  Um was geht es?
- Mit Intent Donations kann die App dem System mitteilen, dass der User eine bestimmte Aktion gemacht hat. So kann das System in Zukunft dem User zum passenden Moment die selbe Aktion vorschlagen:

![][image-1]

##  An welchen Stellen werden die Vorschläge angezeigt?

- Suggestions
- Shortcuts
- Focus
- Smart Stack
- Siri

Beispiel: Seit iOS 15 gibt es Widget Suggestions für den Smart Stack: Zum Beispiel für eine Wetter-App, welche das Wetter für einen bestimmten Ort anzeigen möchte. Das System entscheidet dann zum Beispiel, dass es am besten ist, das Widget für einen bestimmten Ort zu einer bestimmten Zeit anzuzeigen:
![][image-2]

##  Hinweis

- Wenn der User eine Aktion über Siri ausführt, muss man keinen Intent mehr "spenden", das System weiss bereits von der Interaktion.
- Pro Aktion sollte man nicht mehrere Donations machen.
- Wenn jede Donation andere Parameter hat, dann kann das System nicht daraus lernen, weil es immer wie eine neue Donation aussieht. Deshalb kann man angeben, dass nur bestimmte Parameter zum lernen  verwendet werden sollen:
![][image-3]

![][image-4]

- Man kann Donations auch löschen


## Donations testen
- In den Developer-Settings auf dem Gerät gibt es zwei Optionen:
	- Display Recent Shortcuts
	- Display Donations on Lock Screen

## Weiterführende Informationen
- To learn more about adding phrases to Siri, see [Shortcut-Related UI][1].
- [https://developer.apple.com/documentation/sirikit/donating\_shortcuts][2]

##  Zusammenfassung
- Konzept: Für was sind Intent Donations gut?

[1]:	https://developer.apple.com/documentation/sirikit/shortcut-related_ui "Shortcut-Related UI"
[2]:	https://developer.apple.com/documentation/sirikit/donating_shortcuts

[image-1]:	assets/Bildschirmfoto%202024-02-19%20um%2006.57.40.png
[image-2]:	assets/Bildschirmfoto%202024-02-19%20um%2006.56.46.png
[image-3]:	assets/Bildschirmfoto%202024-02-19%20um%2007.04.10.png
[image-4]:	assets/Bildschirmfoto%202024-02-19%20um%2007.04.43.png

#learning unit#