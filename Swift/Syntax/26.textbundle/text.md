# Generic Constraints ✋
::26::

## Type Constraints

```swift
func someFunction<T: SomeClass, U: SomeProtocol>(someT: T, someU: U) {
    // function body goes here
}
```

## Contextual Where Clauses

```swift
func anyCommonElements<T: Sequence, U: Sequence>(_ lhs: T, _ rhs: U) -> Bool
    where T.Element: Equatable, T.Element == U.Element
{ /*...*/ }
```
(Beachte `Element` ist wiederum der generische Typ von `T`)

> Writing `<T: Equatable>` is the same as writing `<T> ... where T: Equatable`.

## Contextual Extension

```swift
extension Container where Item == Int {
	//....
}
```

Man könnte das ganze auch so machen:

```swift
extension Container {
    func average() -> Double where Item == Int {
		//....
    }
}
```
(Vermutlich wird diese Funktion jetzt nur für Container mit dem generischen Typ `Int` hinzugefügt)

## Zusammenfassung
Type Constraints
Contextual Where Clauses
Contextual Extension