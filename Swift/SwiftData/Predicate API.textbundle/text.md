# Predicate API
🔎


## Wie funktioniert das Predicate Makro?

- Es sieht aus als wäre es purer Swift Code. Im Hintergrund wird es aber in SQL konvertiert. Deshalb sind nicht alle Ausdrücke möglich.
- Vorteil im Vergleich zu `NSPredicate`: Es ist Typensicher
- Es es wird nicht alles unterstützt, zum Beispiel `contains` oder `starts(with: )` oder `localizedUppercase` ist unterstützt, aber `hasPrefix()` und `hasSuffix()` und `uppercased` wird nicht unterstützt.
- Predicates müssen aus einem einzigen Ausdruck bestehen

## Ein Swift Data Query Filtern

### Statisch
```swift
@Query(filter: #Predicate<Destination> { destination in
    destination.priority > 2
}) var destinations: [Destination]
```

###  Dynamisch
```swift
@Query var destinations: [Destination]

init(minPriority: Int) {

	let myPredicate = #Predicate<Destination> {
		$0.priority >= minPriority
	}
	
	 _destinations = Query(filter: myPredicate)
}
```

=\> Man kann es auch dynamisch Filtern, dazu muss man einfach im Initializer einen Such-String übergeben und diesen dann verwenden....

##  Ein Array Filtern

```swift
let pred = #Predicate<Person> {
    $0.favoriteColor == .blue
}
```

```swift
let blueLovers = people.filter(pred)
```


## Details
[https://www.hackingwithswift.com/quick-start/swiftdata/how-to-filter-swiftdata-results-with-predicates][1]


## Zusammenfassung
- Ein Swift Data Query mit Predicate erstellen
- Eine Liste von `Person` mit einem Predicate filtern. (Nur Personen mit `favoriteColor == blue`)

[1]:	https://www.hackingwithswift.com/quick-start/swiftdata/how-to-filter-swiftdata-results-with-predicates

#Swift5.9# #learning unit# #Daten