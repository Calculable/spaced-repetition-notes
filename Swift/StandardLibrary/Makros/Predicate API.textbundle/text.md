# Predicate API
🔎

```swift
let pred = #Predicate<Person> {
    $0.favoriteColor == .blue
}
```

Vorteil im Vergleich zu `NSPredicate`: Es ist Typensicher

##  Mit Predicate Filtern
```swift
let blueLovers = people.filter(pred)
```

## Zusammenfassung
- Eine Liste von `Person` mit einem Predicate filtern. (Nur Personen mit `favoriteColor == blue`)

#Swift5.9# #learning unit#