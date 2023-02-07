# Lazy Stored Properties
ℹ️

> A lazy stored property is a property whose initial value isn’t calculated until the first time it’s used.
```swift
class DataManager {
    lazy var importer = DataImporter()
```

Hinweis zu Multithreading: If a property marked with the lazy modifier is accessed by multiple threads simultaneously and the property hasn’t yet been initialized, there’s no guarantee that the property will be initialized only once.

Das kann sehr praktisch sein, wenn ein Objekt sich selbst im Konstruktor der lazy variable mitgeben will!

## Zusammenfassung
Codebeispiel