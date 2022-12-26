# Properties
::11::

## Computed Properties / Setter- und Getter

```swift
 var perimeter: Double {
        get {
            return 3.0 * sideLength //alternativ: ohne return
        }
        set { //alternativ set(myNewVariableName)
            sideLength = newValue / 3.0 //beachte: newValue
        }
 }
```
(Kann auch nur Read- oder Write-Only sein)

## Observed Properties: willSet und didSet

```swift
var triangle: EquilateralTriangle {
        willSet { //beachte: newValue
            square.sideLength = newValue.sideLength
        }
		didSet { //hier wird old-value verwendet
			
		}
}
```

## Lazy Stored Properties

> A lazy stored property is a property whose initial value isn’t calculated until the first time it’s used.
```swift
class DataManager {
    lazy var importer = DataImporter()
```

Hinweis zu Multithreading: If a property marked with the lazy modifier is accessed by multiple threads simultaneously and the property hasn’t yet been initialized, there’s no guarantee that the property will be initialized only once.

## Type Properties

- Automatisch Lazy
- Sicher für Multithreading
- `static`: nicht überschreibbar durch unterklasse
- `class`: überrschreibbar durch Unterklasse

```swift
class SomeClass {
    static var storedTypeProperty = "Some value."
    class var overrideableComputedTypeProperty: Int = 107
}
```
