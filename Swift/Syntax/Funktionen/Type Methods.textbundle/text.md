# Type Methods
👤
> You indicate type methods by writing the `static` keyword before the method’s func keyword. Classes can use the class keyword instead, to allow subclasses to override the superclass’s implementation of that method.

```swift
class SomeClass {
    class func someTypeMethod() { //static wenn es nicht überschrieben werden soll
        // type method implementation goes here
    }
}
SomeClass.someTypeMethod()
```

- `self` zeigt dan auf den Typen und nicht auf die Instanz (Man kann also nur Type-Properties und Type-Methods aufrufen)

##  Zusammenfassung
- Unterschied `class` und `static`

#learning unit#