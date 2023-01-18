# @SceneStorage

Eigentlich gleich wie AppStorage mit dem Unterschied, dass jede Scene eine eigene Instanz hat (zum Beispiel auf dem iPad wenn die App Side-By-Side läuft):

```swift
@SceneStorage("text") var text = ""
```

> So, you might use  `@AppStorage`  to store global values such as “what is the user’s high score?”, and you might use  `@SceneStorage`  to store “what page is the user reading right now?”


## Zusammenfassung
- Code und Zweck
