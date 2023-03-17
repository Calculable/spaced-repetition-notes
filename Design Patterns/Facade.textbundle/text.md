
# Facade
🏠

## Zweck

- Wenn man mit komplizierten Bibliotheken und API’s arbeitet
- Ein einfaches Interface für mehrere komplizierte Subsysteme zur Verfügung stellen
- Die Facade kümmert sich auch um den Lifecycle

```swift
class Facade { 
   func operation() -> String {
        var result = "Facade initializes subsystems:"
        result += " " + subsystem1.operation1()
        result += " " + subsystem2.operation1()
        result += "\n" + "Facade orders subsystems to perform the action:\n"
        result += " " + subsystem1.operationN()
        result += " " + subsystem2.operationZ()
        return result
    }
}
```

## Zusammenfassung
- Zweck


#nur learning unit# #learning unit#