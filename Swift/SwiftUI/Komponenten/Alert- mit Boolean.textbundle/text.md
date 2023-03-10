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

## Hinweis

- Anscheinend kann man nicht mehrere `alert` Modifier aneinander hängen.
- Lösung: Man hängt die Modifiers einfach an unterschiedliche Views.

## Zusammenfassung
- Wie macht man einen Alert mit Bool?
- Wie ist ein Alert mit Buttons und Inhalt aufgebaut?