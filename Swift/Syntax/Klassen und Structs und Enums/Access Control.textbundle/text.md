# Access Control
✋

## Syntax

```swift
open class SomePublicClass {}
public class SomePublicClass {}
internal class SomeInternalClass {} //wäre auch implizit
fileprivate class SomeFilePrivateClass {}
private class SomePrivateClass {}

public var somePublicVariable = 0
internal let someInternalConstant = 0 //wäre auch implizit
fileprivate func someFilePrivateFunction() {}
private func somePrivateFunction() {}
```

##  Zugriffsrechte

- Open: Zugriff von anderen Modulen
- Public: Ausserhalb des Modus kann man es nicht erben oder überschreiben
- Package: Zugriff innerhalb des Package
- Internal: (Default) Zugriff innerhalb des Moduls und in den tests
- File Private: Zugriff innerhalb des gleichen Files
- Private: Zugriff innerhalb der gleichen Enclosing Declaration

## Zusammenfassung
- Welche Auswirkung haben Open, Public, Package, Internal, File Private und Private

#learning unit# #guide