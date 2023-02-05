# Funktionen 🤖

## Funktion definieren und aufrufen

### ohne eigenes Label
```swift
func greet(person: String, day: String) -> String {
    //...
}
greet(person: "Bob", day: "Tuesday")
```

### mit eigenem Label
Standartmässig gilt: Variabelname = Label
```swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

## Parameter

## Zusammenfassung
Mit und ohne Label
