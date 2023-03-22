# Toolbar
🧩

## Ohne Placement
```swift
.navigationTitle("BetterRest")
.toolbar {
    Button("Calculate", action: calculateBedtime)
}
```

![][image-1]

## Mit Placement
- Zum Beispiel `.primaryAction` oder `.secondaryAction`
- Man wrappt das ganze in ein `ToobarItem`


```swift
.toolbar {
	ToolbarItem(placement: .primaryAction) {
		Button("Example") {}		
	}
}
```





## Benutzerdefinierte Toolbar
Man kann die Toolbar auch für den Nutzer anpassbar machen:

 [How to let users customize toolbar buttons - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-let-users-customize-toolbar-buttons)


## Zusammenfassung
- Wie macht man eine Toolbar





[image-1]:	assets/Bildschirmfoto%202022-07-23%20um%2009.31.54.png

#learning unit#