# MVVM
🏛️

## Beispiel

```swift
extension ContentView {
    @MainActor class ViewModel: ObservableObject {
        @Published private(set) var locations = [Location]()
        @Published private(set) var selectedPlace: Location?
    }
}
```


```swift
extension ContentView {
    @MainActor class ViewModel: ObservableObject {
        @Published var mapRegion = MKCoordinateRegion(center: CLLocationCoordinate2D(latitude: 50, longitude: 0), span: MKCoordinateSpan(latitudeDelta: 25, longitudeDelta: 25))
        @Published var locations = [Location]()
        @Published var selectedPlace: Location?
    }
}
```

- Man kann die ganzen State Properties in das ViewModel verschieben. ACHTUNG: `@State private` muss man jetzt durch `@Published` ersetzen.
- Man macht eine Extension damit man nicht den Namespace verschmutzt

## ViewModel in der View erzeugen

```swift
@StateObject private var viewModel = ViewModel()
```

Das ViewModel muss aber nicht immer zwingend von der View selbst erstellt werden. Es kann auch über Dependency Injection in die App kommen.

## Siehe auch

Kapitel: „MVVM: Diskussion“
## Zusammenfassung
- Wie sieht ein einfaches ViewModel aus? Wie dessen Properties?, Wie die Access-Rechte?
- Wie erstellt man ein ViewModel in der View?