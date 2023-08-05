# Synthesized Implementation
🤖

- Für einige Swift-Protokolle gibt es Synthesized Implementationen.
- Das heisst man muss es nicht selbst implementieren (bei Structs)
- Beispielsweise kann man ein Struct ganz einfach zu `Equatable` konform machen, wenn die einzelnen Properties ebenfalls `Equatable` sind:

```swift
extension MyStruct: Equatable { }
```

Das gleiche funktioniert auch mit `Hashable` und `Codable`

Wenn man generische Typen hat, weiss man ja nicht im voraus, ob der generische Typ dem Protokoll entspricht. Hier kann man einfach Conditional Conformance verwenden:

```swift
extension MyStruct: Equatable where Value: Equatable { }
```

Welchen Anforderungen eine Klasse/Struct/Enum genügend muss um das Feature zu nutzen steht hier: [https://docs.swift.org/swift-book/LanguageGuide/Protocols.html][1]


## Zusammenfassung
- Was sind Synthesized implementationen?
- Beispiel: Was muss ein Struct erfüllen, dass `Equatable` automatisch implementiert werden kann?

[1]:	https://docs.swift.org/swift-book/LanguageGuide/Protocols.html

#learning unit#