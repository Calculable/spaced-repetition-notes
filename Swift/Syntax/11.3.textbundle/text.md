# Type Properties ℹ️
::11.3::

## Type Properties

- Automatisch Lazy
- Sicher für Multithreading
- `static`: nicht überschreibbar durch unterklasse
- `class`: überschreibbar durch Unterklasse

```swift
class SomeClass {
    static var storedTypeProperty = "Some value."
    class var overrideableComputedTypeProperty: Int = 107
}
```



## Zusammenfassung
Codebeispiel