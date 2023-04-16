# Table
🗒️
```swift
Table(smoothies, selection: Selection) {
	TableColumn("Name", value: \.title).width (200)
	TableColumn("Ingredients", value: \.ingredientsList)
	TableColumn("Calories") { smoothie in
		Text(smoothie.kilocalories.formatted ())
	}.width(100)
}
```

## Zusammenfassung
 -Wie macht man eine Tabelle in SwiftUI?

#learning unit#