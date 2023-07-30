# SwiftUI: Custom View innerhalb einer List
💡

```swift
List {
    Section() {
        Text("Das ist ein Beispiel-Text")
            .fontDesign(.rounded)
            .font(.title)
    }
    .listRowBackground(EmptyView())
    
	Text("First")
    Text("Second")
}
```

![][image-1]

## Zusammenfassung
- SwiftUI wie kann man zusätzlich zu einer Liste noch weitere Informationen anzeigen? (Code)

[image-1]:	assets/Bildschirmfoto%202023-07-27%20um%2012.49.06.png

#learning unit#