# Synthesized Implementation
🤖

- Für einige Swift-Protokolle gibt es Synthesized Implementationen.
- Das heisst man muss es nicht selbst implementieren (bei Structs)
- Beispielsweise kann man ein Struct ganz einfach zu `Equatable` konform machen, wenn die einzelnen Properties ebenfalls `Equatable` sind:

```swift
extension MyStruct: Equatable { }
```

Das gleiche funktioniert auch mit `Hashable` und \`Codable\`\`

Wenn man generische Typen hat, weiss man ja nicht im voraus, ob der generische Typ dem Protokoll entspricht. Hier kann man einfach Conditional Conformance verwenden:

```swift
extension MyStruct: Equatable where Value: Equatable { }
```


## Zusammenfassung
- Was sind Synthesized implementationen?
- Beispiel: Was muss ein Struct erfüllen, dass `Equatable` automatisch implementiert werden kann?


#nur learning unit# #learning unit#