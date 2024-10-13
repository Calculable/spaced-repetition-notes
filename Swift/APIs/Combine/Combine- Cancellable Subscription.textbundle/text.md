# Combine: Cancellable Subscription
🔀

## Subscription erhalten
Wenn man einen Subscriber anwendet, bekommt man eine Subscription zurück (welche zum Protokoll `Cancellable` konform ist):

```swift
let canceller: AnyCancellable = myPublisher
    .assign(to: \.someProperty, on: someObject)
```

**Die Referenz muss man sich speichern damit die Subscription nicht verloren geht. **Wenn man keine Referenz mehr auf die Subscription hält (zum Beispiel weil das Parent-Objekt aus dem Speicher entfernt wurde), dann werden auch keine neuen mehre mehr empfangen.

## Eine Subscription beenden

###  Variante: Finaler Wert wird gesendet
Eine Subscription wird auch automatisch beendet wenn der Publisher einen finalen Wert sendet.

###  Variante: Subscription explizit beenden
Man kann die Subscription auch selbst beenden:

```swift
canceller.cancel()
```

###  Variante: Man hat keine Referenz mehr auf die Subscription
Beispiel: Wenn man keine Referenz auf `canceller` mehr hat (zum Beispiel weil die View welche die Referenz enthält nicht mehr existiert), dann wird die Subscription ebenfalls beendet. (Im `deinit` von `AnyCancellable` wird `cancel` aufgerufen)

##  Mehrere Subscriptions
Wenn man mehrere Subscriptions in einer verwaltet, dann kann man sie so zuweisen:

```swift
private var cancellables: Set<AnyCancellable> = []
```

```swift
myPublisher
	.assign(to: \.someProperty, on: someObject)
	.store(in: &cancellables)
```

> The AnyCancellable class calls cancel() on deinit and makes sure subscriptions terminate early. 

## Quelle

[https://developer.apple.com/documentation/combine/published][1]
[https://www.avanderlee.com/swift/combine/][2]


## Zusammenfassung
- Warum muss man bei Combine oftmals ein Set\<AnyCancellable\>?

[1]:	https://developer.apple.com/documentation/combine/published
[2]:	https://www.avanderlee.com/swift/combine/

#learning unit# #guide