# Table
🗒️

## Code
```swift
Table(smoothies, selection: Selection) {
	TableColumn("Name", value: \.title).width (200)
	TableColumn("Ingredients", value: \.ingredientsList)
	TableColumn("Calories") { smoothie in
		Text(smoothie.kilocalories.formatted ())
	}.width(100)
}
```


##  Einschränkung
Achtung, unter iOS zeigen die Tabellen nur die erste Spalte!

## Zusammenfassung
- Wie macht man eine Tabelle in SwiftUI?
- Was ist eine Einschränkung auf dem iPhone?

#learning unit#