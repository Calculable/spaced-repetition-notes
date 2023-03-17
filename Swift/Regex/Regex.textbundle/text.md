# Regex
🧿

- Regex Literals erstellen (Vorteil?)
- Explizite Regex
- Weitere Möglichkeit um Regex zu erstellen?


## Regex Literals


```swift
/[a-z]at/
```

Vorteil: Es kann zur Compile-Zeit überprüft werden, ob es gültig ist

## Modifiers

```swift
/the (.*) sat on the (.*)/.ignoresCase(true)
```

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

## Zusammenfassung
- 3 Varianten, um Reguläre ausdrücke zu erstellen (nicht auswändig)
- Wie macht man modifiers

#learning unit#