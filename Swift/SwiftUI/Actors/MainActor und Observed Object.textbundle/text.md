# MainActor und Observed Object

##  Zweck des MainActors

- Nur der MainActor kann das UI anpassen

## Beispiel

```swift
@MainActor
class AccountViewModel: ObservableObject {
    @Published var username = "Anonymous"
    @Published var isAuthenticated = false
}
```


## @StateObject und @ObservedObject laufen automatisch auf dem MainActor

- …auch ohne @MainActor Annotation! 
- Trotzdem sollte man die Annotation schreiben

##  Warum schreibt man @MainActor bei ObservedObjects trotzdem?

Die implizite Arbeit von @StateObject und @ObservedObject auf dem MainActor läuft  nur so lange gut, wie man die Objekte nur über das View manipuliert. Es funktioniert nicht, wenn die Objekte an anderer Stelle bearbeitet werden. Deshalb sollte man auf Nummer sicher gehen.

## Opt-Out

- Mann kann immer noch `nonisolated` verwenden, wenn man bestimmten Code doch nicht unter dem Main-Actor ausführen möchte.


##  Zusammenfassung
- Wie annotiert man ein ViewModel als MainActor?
- Warum braucht es diese Annotation?
- Was geschieht, wenn man diese Annotation nicht macht?

#learning unit#