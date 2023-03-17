# Protokoll: identifiable
📜 

## Beispiel
Es braucht eine `id`-Property


```swift
class Boid: Identifiable {
    let id = UUID()
	//...
}
```

## Zweck

Das Protokoll hilft uns, wenn man zum Beispiel mit `ForEach` in SwiftUI durch eine Sammlung von Objekten loopen möchte. SwiftUI braucht ein Property, um die einzelnen Objekte voneinander unterscheiden zu können.

## Zusammenfassung
- Welche Anforderung hat das Protokoll `identifiable`?
- Wozu ist dieses Protokoll gut?


#nur learning unit# #learning unit#