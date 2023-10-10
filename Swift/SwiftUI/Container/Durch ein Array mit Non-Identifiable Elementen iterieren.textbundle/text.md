# Durch ein Array mit Non-Identifiable Elementen iterieren
🔁

## Variante 1: Indices
```swift
ForEach(people.indices, id: \.self) { index in
	Text("\(index) \(people[index])")
}
```

## Variante 2: Enumerated
```swift
ForEach(Array(people.enumerated()), id: \.offset) { index, person in
    Text("Person \(index): \(person.name)")
}
```


## Zusammenfassung
- Welche zwei Varianten gibt es, um das zu machen?

#learning unit#