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

## Zusammenfassung
- JSON encodieren und decodieren

#learning unit#