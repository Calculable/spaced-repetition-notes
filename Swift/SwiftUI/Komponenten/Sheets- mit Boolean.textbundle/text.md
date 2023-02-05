# Sheets: mit Boolean 📃

## Anzeigen: mit Boolean
```swift
struct ContentView: View {
    @State private var showingSheet = false

    var body: some View {
        Button("Show Sheet") {
            showingSheet.toggle()
        }
        .sheet(isPresented: $showingSheet) {
            SecondView()
        }
    }
}
```


## Zusammenfassung
Wie macht man ein Sheet mit Boolean?
