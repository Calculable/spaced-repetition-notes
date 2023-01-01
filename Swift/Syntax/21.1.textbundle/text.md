# Regex 🧿
::21.1::

- Regex Literals erstellen (Vorteil?)
- Explizite Regex
- Weitere Möglichkeit um Regex zu erstellen?


## Regex Literals


```swift
/[a-z]at/
```

Vorteil: Es kann zur Compile-Zeit überprüft werden, ob es gültig ist

## Explizite Regex


```swift
let atSearch = try Regex("[a-z]at")
```

## Regex Builder (nicht auswändig)

```swift
import RegexBuilder

let search3 = Regex {
    "My name is "

    Capture {
        OneOrMore(.word)
    }

    " and I'm "

    Capture {
        OneOrMore(.digit)
    }

    " years old."
}
```

## String Methoden

Viele String-Methoden funktionieren sowohl mit Regex als auch ohne Regex:
```swift
print(message.replacing("cat", with: "dog"))
```

```swift
print(message.replacing(/[a-m]at/, with: "dog"))
```

## Zusammenfassung
Regex Literals (Vorteil?)
Explizite Regex
Weitere Möglichkeit um Regex zu erstellen?