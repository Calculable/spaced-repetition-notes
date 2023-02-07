# ObservableObject
🕵️

## Zweck
- @State funktioniert nur mit Structs, deshalb gibt es Observable Objec 
- Primär wenn man eine Klassenreferenz an mehreren Orten braucht


## Beispiel
```swift
@MainActor class User: ObservableObject {
    @Published var firstName = "Bilbo"
    @Published var lastName = "Baggins"
}
```

(@MainActor macht man sehr häufig)

## ObservableObject in der View verwenden

```swift
@StateObject var user = User() //wird verwendet wenn das Objekt hier erstellt wird

@ObservedObject var user; //wird verwendet, wenn das Objekt an einer anderen Stelle verwendet wird
```

## Zusammenfassung
- Wie ist ein ObservableObject aufgebaut?
- Wann verwendet man StateObject und wann ObservedObject?
- Was wird oft gemeinsam mit dem ObservableObject Protokoll verwendet?