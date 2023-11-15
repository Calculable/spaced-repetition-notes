# localizedStandardCompare
🎱

- Es ist ein Funktion auf dem String, welcher wie der Finder sortiert
- Ist der Standart Comperator für String-Vergleiche
- Beispiel:

	- User 1
	- User 2
	- User 11
	- User 12
	- User 110

- Alphabetisch wäre die Reihenfolge anderst!



##  Link

[https://developer.apple.com/documentation/foundation/nsstring/1409742-localizedstandardcompare][1]

##  Code

```swift
let names = ["Åsa", "Øystein", "Aron", "Zelda", "äron"]

let sortedNames = names.sorted { (s1, s2) -> Bool in
    return s1.localizedStandardCompare(s2) == .orderedAscending
}

print(sortedNames)
```

##  Zusammenfassung
- Was macht das? (ohne Code)

[1]:	https://developer.apple.com/documentation/foundation/nsstring/1409742-localizedstandardcompare

#learning unit#