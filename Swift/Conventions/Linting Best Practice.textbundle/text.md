# Linting Best Practice
🖨️

## Beispielformat: Lange Signatur

```swift
func decode<T: Decodable>(
    _ type: T.Type,
    from file: String,
    dateDecodingStrategy: JSONDecoder.DateDecodingStrategy = .deferredToDate,
    keyDecodingStrategy: JSONDecoder.KeyDecodingStrategy = .useDefaultKeys
) -> T {
```

## Alternative: colon alignment

Einige bevorzugen auch **colon alignment** - das ist jedoch nicht kompatibel mit SwiftLint

```swift
func decode<T: Decodable>(
                  _ type: T.Type,
               from file: String,
    dateDecodingStrategy: JSONDecoder.DateDecodingStrategy = .deferredToDate,
     keyDecodingStrategy: JSONDecoder.KeyDecodingStrategy = .useDefaultKeys
) -> T {
```


## Zusammenfassung
- Wie kann man lange Funktionssignaturen formatieren (zwei Varianten)

#learning unit#