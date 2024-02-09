# Tab View
🏡

### Beispiel
```swift
TabView {
    Text("Tab 1")
        .tabItem {
            Label("One", systemImage: "star")
        }

    Text("Tab 2")
        .tabItem {
            Label("Two", systemImage: "circle")
        }
}
```

### Programmatisch zwischen den Tabs umschalten
```swift
struct ContentView: View {
    @State private var selectedTab = "One"

    var body: some View {
        TabView(selection: $selectedTab) {
            Text("Tab 1")
                .onTapGesture {
                    selectedTab = "Two"
                }
                .tabItem {
                    Label("One", systemImage: "star")
                }
                .tag("One")

            Text("Tab 2")
                .tabItem {
                    Label("Two", systemImage: "circle")
                }
                .tag("Two")
        }
    }
}
```

Jetzt kann man einfach `selectedTab` ändern. 

### Tab View und Navigation View Kombinieren

- Geht ohne Probleme
- Tab View ist in der Regel die äusserste Hierarchiestufe


##  Zusammenfassung
- Wie macht man eine Tab View?


#learning unit#