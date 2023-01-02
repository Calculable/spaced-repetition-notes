
# Factory Method 🏭

## Beispiel

- Man lagert das Erstellen von Objekten aus
- Hinweis: Die Factory kann auch Businesscode beinhalten, der auf den erzeugen Objekten basiert

```swift
protocol Factory {
    func factoryMethod() -> Product //wenn man möchte, kann man auch eine Default Impleentation machen
    func someOperation() -> String
}
```

Hier kommt die Business-Logik rein, das ist der eigentlich interessante teil, weil darin die Factory-Methode aufgerufen wird:
```swift
extension Factory {
    func someOperation() -> String {
        // Call the factory method to create a Product object.
        let product = factoryMethod()

        // Now, use the product.
        return "Creator: The same creator's code has just worked with " + product.operation()
    }
}
```

Die einzelnen Implementationen erzeugen unterschiedliche Objekte
```swift
class ConcreteFactory1: Creator {
    public func factoryMethod() -> Product {
        return ConcreteProduct1()
    }
}
```

```swift
class ConcreteFactory2: Creator {
    public func factoryMethod() -> Product {
        return ConcreteProduct2()
    }
}
```


So kann der Code dann verwendet werden
```swift
class Client {
    // ...
    static func someClientCode(factory: Factory) {
        print("Client: I'm not aware of the creator's class, but it still works.\n"
            + creator.someOperation())
    }
    // ...
}
```


```swift
Client.someClientCode(factory: ConcreteFactory1())
```

Achtung wichtig - beachte: Der Client ruft hier nicht die factoryMethod auf, sondern direkt den Business code!  Hinweis - es gibt aber auch viele Beispiele, indem die Factory/Creator primär verwendet wird, um direkt die Products zu erhalten und nicht um business Logik auf der Factory selbst aufzurufen:


## Zusammenfassung
- Zweck
- Beispielcode