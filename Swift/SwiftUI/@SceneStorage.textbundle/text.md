# @SceneStorage
💾

##  Code
Eigentlich gleich wie AppStorage mit dem Unterschied, dass jede Scene eine eigene Instanz hat (zum Beispiel auf dem iPad wenn die App Side-By-Side läuft):

```swift
@SceneStorage("text") var text = ""
```

> So, you might use  `@AppStorage`  to store global values such as “what is the user’s high score?”, and you might use  `@SceneStorage`  to store “what page is the user reading right now?”

##  Beispiel

Beispiel: Man hat eine Navigation View und verwendet App Storage, um zu speichern welcher Tab geöffnet ist, um diesen beim erneuten Starten der App wiederherstellen zu können. Hätte man jetzt mehrere Instanzen der App gleichzeitig am laufen, dann würde dies bedeuten, dass der Wechsel eines Tabs der einen Applikation auch den Wechsel in der anderen Applikation auslösen würde. Deshalb verwendet man hier Scene Storage

## Weiterer Unterschied

- Wenn der Nutzer die App über den App-Switcher abschiesst, werden die Daten entfernt!
## Zusammenfassung
- Code und Zweck


#learning unit#