# Template Method
📑

## Zweck

- Oft verwendet in Swift Frameworks
- Damit Framework User mit Vererbung die Frameworks erweitern können

> Template Method can be recognized if you see a method in base class that calls a bunch of other methods that are either abstract or empty.

## Beispiel

```swift
protocol AbstractProtocol {

    /// The template method defines the skeleton of an algorithm.
    func templateMethod()

    /// These operations already have implementations.
    func baseOperation1()
    func baseOperation2()
    func baseOperation3()

    /// These operations have to be implemented in subclasses.
    func requiredOperations1()
    func requiredOperation2()

    /// These are "hooks." Subclasses may override them, but it's not mandatory
    /// since the hooks already have default (but empty) implementation. Hooks
    /// provide additional extension points in some crucial places of the
    /// algorithm.
    func hook1()
    func hook2()
}

extension AbstractProtocol {

    func templateMethod() {
        baseOperation1()
        requiredOperations1()
        baseOperation2()
        hook1()
        requiredOperation2()
        baseOperation3()
        hook2()
    }

    /// These operations already have implementations.
    func baseOperation1() {
        ///...
    }

    func baseOperation2() {
        ///...
    }

    func baseOperation3() {
        ///...
    }

	///Hooks can be overriden but don't have to be
    func hook1() {}
    func hook2() {}
}
```

## Zusammenfassung
- Zweck
- Beispielcode
- Begriffe: Base, Hook

#learning unit#