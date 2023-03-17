# Generics: Contextual Where Clauses
✋

```swift
func anyCommonElements<T: Sequence, U: Sequence>(_ lhs: T, _ rhs: U) -> Bool
    where T.Element: Equatable, T.Element == U.Element
{ /*...*/ }
```
(Beachte `Element` ist wiederum der generische Typ von `T`)

> Writing `<T: Equatable>` is the same as writing `<T> ... where T: Equatable`.


#learning unit#