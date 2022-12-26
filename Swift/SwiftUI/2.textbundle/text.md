# ObservableObject
::2::

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

## Änderungen manuell publishen

So braucht man zum Beispiel `@Published` nicht mehr:

```swift
var value = 0 {
    willSet {
        objectWillChange.send()
    }
}
```

Man sollte es aufrufen BEVOR man etwas ändert. So kann Swift das UI analysieren.

## ObservableObject in der View verwenden

```swift
@StateObject var user = User() //wird verwendet wenn das Objekt hier erstellt wird

@ObservedObject var user; //wird verwendet, wenn das Objekt an einer anderen Stelle verwendet wird
```

