# Inspector

## Code
```swift
struct ContentView: View {
    @State private var showingInspector = false
    var body: some View {
        Button("Toogle Inspector") {
            isShowingInspector.toggle()
        }
        .font(.largeTitle)
        .inspector(isPresented: $showingInspector) {
            Text("Hello!")
        }
    }
}
```


## Resultat
![][image-1]![][image-2]

## Grösse festlegen

```swift
.inspector(isPresented: $showingInspector) {
	Text("Inspector View")
		.inspectorColumnWidth(min: 100, ideal: 150, max: 200)
}
```

- Der Nutzer kann die Grösse auch selbst verstellen
- Die Konfiguration bezieht sich also vor allem auf die erste Anzeige es Inspectors

## Zusammenfassung
- Inspector einblenden
- Unterschied zwischen iPhone und iPad

[image-1]:	assets/2023-06-18%2007.22.54.gif
[image-2]:	assets/2023-06-18%2007.38.08.gif

#learning unit# #iOS17