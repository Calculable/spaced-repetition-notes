# NavigationStack mit Programatic Navigation  🧭

## Codebeispiel

```swift
NavigationStack(path: $path) {
    List {
        NavigationLink("Purple", value: Color.purple)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Orange", value: Color.orange)
    }
    .navigationDestination(for: Color.self) { color in
        Text(color.description)
    }
}
```

## Zusammenfassung
- Codebeispiel

#nur learning unit#