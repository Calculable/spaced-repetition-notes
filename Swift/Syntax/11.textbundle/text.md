# Lazy Stored Properties ℹ️
::11::


> A lazy stored property is a property whose initial value isn’t calculated until the first time it’s used.
```swift
class DataManager {
    lazy var importer = DataImporter()
```

Hinweis zu Multithreading: If a property marked with the lazy modifier is accessed by multiple threads simultaneously and the property hasn’t yet been initialized, there’s no guarantee that the property will be initialized only once.


## Zusammenfassung
Codebeispiel