# Encoding / Decoding
📠

## Codierbares Model

```swift
struct User: Codable {
    let firstName: String
    let lastName: String
}
```

## Encoding zu JSON

```swift
let data = try JSONEncoder().encode(user)
```

## Decoding von JSON

```swift
let decodedItems = try JSONDecoder().decode([ExpenseItem].self, from: savedItems)
```

## Wie wird mit Optionals umgegangen?

>  In fact, if we mark a property as optional Codable will automatically skip over it if the value is missing from our input JSON.
## Zusammenfassung
- JSON encodieren und decodieren

#learning unit#