# Previews anzeigen
🎪

##  Code (Neu)

Mit Swift 5.9

```swift
#Preview {
	ContentView()
}
```

Mehrere Previews mit Titel:

```swift
#Preview("Placeholder View 1") {
	AppDetailColumn()
}

#Preview("Placeholder View 2") {
	AppDetailColumn()
}
```

## Funktioniert auf allen Plattformen

![][image-1]

Bei UIKit Kaxnn man auch einen View Controller zurückgeben


## Code (Alt)
```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .environment(\.sizeCategory, .extraSmall)

        ContentView()
			.preferredColorScheme(.dark)

        ContentView()
			.previewDevice(PreviewDevice(rawValue: "iPhone 14 Pro Max"))
			.previewInterfaceOrientation(.landscapeLeft)
    }
}
```

## Tipp

Man kann die Previews auch mit `ForEach` erzeugen.


## Zusammenfassung

- Ein oder mehrere Previews anzeigen
- Wie konfiguriert man das Preview (nur Konzept)

[image-1]:	assets/Bildschirmfoto%202023-06-08%20um%2021.25.40.png

#learning unit#