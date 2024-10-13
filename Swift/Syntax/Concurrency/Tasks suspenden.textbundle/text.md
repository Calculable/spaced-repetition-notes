# Tasks suspenden
✋
- Mit `await` markiert man ja einen potentiellen „suspension point“ im Code
- So kann man weitere suspension points innerhalb eines Tasks definieren:


```swift
for check in 1...number {
    if check.isMultiple(of: 100_000) {
        await Task.yield() //<-
    }

    if number.isMultiple(of: check) {
        result.append(check)
    }
}
```

- Das ist besonders sinnvoll wenn man sich in einem langen Loop befindet und dem System die Möglichkeit geben möchte, anderen Code auszuführen.
- Swift kann entscheiden, ob es es im Thread weitermachen will oder einen anderen Thread bevorzugt
-  yield braucht man nur sehr selten selber weil das idr. einer Library geschieht (z.B. Networking Library)


## Zusammenfassung
- Wie „suspendet“ man einen Task?
- Was ist die Auswirkung / der Zweck?

#learning unit# #guide