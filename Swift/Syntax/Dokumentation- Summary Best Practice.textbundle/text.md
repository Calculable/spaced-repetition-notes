# Dokumentation: Summary Best Practice
📝


## Auf was ist zu achten
- Satzfragment
- Endet mit einem Punkt
- In manchen Fällen können mehrere Satzfragmente mit einem Semikolon getrennt werden

## Beispiel für Funktion

```swift
/// Returns a "view" of `self` containing the same elements in
/// reverse order.
func reversed() -> ReverseCollection
```

```swift
/// Removes and returns the first element of `self` if non-empty;
/// returns `nil` otherwise.
mutating func popFirst() -> Element?
```

## Beispiel für Initializer

Sollte mit „Creates“ beginnen

```swift
/// Creates an instance containing `n` repetitions of `x`.
init(count n: Int, repeatedElement x: Element)
```

##  Beispiel für Structs / Klassen und Properties

Beschreibt, was es ist

```swift
/// A collection that supports equally efficient insertion/removal
/// at any position.
struct List {

  /// The element at the beginning of `self`, or `nil` if self is
  /// empty.
  var first: Element?
  ...
```
