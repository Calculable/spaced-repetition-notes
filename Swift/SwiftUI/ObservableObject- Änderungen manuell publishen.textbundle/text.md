# ObservableObject: Änderungen manuell publishen
🕵️

So braucht man zum Beispiel `@Published` nicht mehr:

```swift
var value = 0 {
    willSet {
        objectWillChange.send()
    }
}
```

Man sollte es aufrufen BEVOR man etwas ändert. So kann Swift das UI analysieren.

## Zusammenfassung
- Wie kann man die View über eine Änderung informieren?