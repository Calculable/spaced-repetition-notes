# Unterschied zwischen Optional\<X\> und X?  🫙

Hier macht der Compiler einen Default-Constructor, welcher nur Name beinhaltet:

```swift
struct User {
    var name: String
    var password: String?
}
```

Hier mach der Compiler einen Default-Constructor der sowohl Name als auch Password beinhaltet:

```swift
struct User {
    var name: String
    var password: Optional<String>
}
```

Ansonsten bleibt es gleich. Man kann es also verwenden um die eigene Intention besser auszurücken.

## Zusammenfassung
- Was ist der Unterschied in der praktischen Verwendung zwischen `Optional<X>` und `X`?


#nur learning unit#