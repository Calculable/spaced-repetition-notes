# Alert: mit Boolean
🧩

##  mit Boolean

```swift
struct ContentView: View {
    @State private var showingAlert = false

    var body: some View {
		Button("Show Alert") {
		    showingAlert = true
		}
		.alert("Important message", isPresented: $showingAlert) {
		    Button("OK", role: .cancel) { }
		} message: {
		    Text("Please read this.")
		}
    }
}
```

![][image-1]

## Hinweis

- Es gibt mehrere Button Roles: `.default`, `.cancel`, `.destructive`
- Anscheinend kann man nicht mehrere `alert` Modifier aneinander hängen.
- Lösung: Man hängt die Modifiers einfach an unterschiedliche Views.
- Wenn man keinen Button angibt, wird einfach ein OK Button hinzugefügt

## Zusammenfassung
- Wie macht man einen Alert mit Bool?
- Wie ist ein Alert mit Buttons und Inhalt aufgebaut?

[image-1]:	assets/Bildschirmfoto%202023-08-09%20um%2008.08.57.png

#learning unit#