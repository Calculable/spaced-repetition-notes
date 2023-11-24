# Sendable
🔒

## Sendable Protokoll

###  Zweck
- Das Protokoll drückt aus, dass ein Typ Thread-Safe ist (zum Beispiel durch interne Locks)

###  Was ist automatisch konform zu Sendable?
- Basisdatentypen (`Int`, `String`, `Bool`, …)
- Optionals
- Standart Library Collections mit den Basis-Datentypen:  `Array<String>` or `Dictionary<Int, String>`
- Tuples
- Actors
- Structs oder Enums, welche nur `Sendable` properties enthalten

```swift
// Implicitly conforms to Sendable
struct MyCustomStruct {
    var mySendableProperty: Int
}
```


### Explicit Conformance
- Wenn man selbst weiss, das der Typ Thread-Safe ist, macht man den Typen selbst konform zu `Sendable`
- Eine Klasse muss dazu
	- Von NSObject oder von nichts erben
	- Ale Properties müssen konstant oder konform zu Sendable sein
	- Die Klasse muss `final` sein

```swift
/// User is immutable and therefore thread-safe, so can conform to Sendable
final class User: Sendable {
    let name: String
    init(name: String) { self.name = name }
}
```

Wenn man die Anforderung nicht erfüllt aber trotzdem weiss, dass es Thread-Safe ist, verwendet man `@unchecked Sendable`

```swift
final class MutableUser: @unchecked Sendable {/*...*/}
```


## Verwendung @Sendable

Ein Closure erwarten, nur Thread-Safe Parameter hat

```swift
func filteredArticles(_ isIncluded: @Sendable (Article) -> Bool) async -> [Article] {
        // ...
}
```

Das heisst, man darf beim Aufruf nur Thread-Safe variablen verwenden:
```swift
let filteredArticles = await listOfArticles.filteredArticles { article in
	//hier dürfen jetzt nur Thread-Safe Werte capturen 
}
```

Häufiger Anwendungsfall ist das Closure, das man in einen Task gibt, dieses muss `@Sendable` sein:

```swift
Task { /*Inhalt*/ }  //funktioniert also nur wenn der Inhalt @Sendable ist
```

##  Build Setting

![][image-1]

> This build setting controls the compiler enforcement level of Sendable and actor-isolation checking.

## Zusammenfassung
- Wozu wird `Sendable` und `@Sendable` verwendet (nur Konzept)

[image-1]:	assets/Bildschirmfoto%202023-08-02%20um%2008.17.26.png

#learning unit#