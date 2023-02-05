# Previews anzeigen 🎪

## Code
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


#nur learning unit#