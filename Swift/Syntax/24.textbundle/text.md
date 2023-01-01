# Precondition / Assertion / Fatal Error 🚔
::24::

## Precondition (for Production)

- Ausgelöster Fehler kann nicht gefangen werden
- Wird in Debug- und Production-Builds geprüft 
- App wird beendet wenn Anforderung nicht erfüllt

```swift
precondition(index > 0, "Index must be greater than zero.")
```

## Assertion (for Development)

- Ist auch eine gute Dokumentation
- Ausgelöster Fehler kann nicht gefangen werden
- Wird nur in Debug-Builds geprüft

```swift
assert(age >= 0, "A person's age can't be less than zero.")
assert(age >= 0)
assertionFailure("failt") //failt immer
```

## FatalError

- Assertion kann ausgeschaltet werden, wenn es im `unchecked` mode kompiliert wird. FatalError kann hingegen nie wegoptimiert werden.
- Benötigt kein `thorws` (vermutlich)
- Für Fehler verwenden, die nie auftreten sollten

```swift
fatalError("Could not load start.txt from bundle.")
```


## Zusammenfassung
Precondition, Assertion, Fatal Error