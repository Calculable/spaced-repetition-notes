# Strings: Behind the scenes
🎭

## Wie sind Strings gespeichert?
> Swift strings are complex collections of characters, where multiple symbols might combine together to a form a single letter visible to users. For example, an emoji as simple as the British flag is actually made up of two distinct unicode characters.

=\> Die `count`-Methode gibt nur 1 zurück, so wie man es aus Nutzer-Sicht erwarten würde.

## Was ist die Implikation davon?
Aus diesem Grund kann man auch nicht mit einem Index auf den Buchstaben zugreifen, Wenn man möchte, kann man sich jedoch eine Helper-Funktion dafür bauen:

```swift
extension String {
    subscript(i: Int) -> Character {
        return self[index(startIndex, offsetBy: i)]
    }
}
```

## Vorsicht: Laufzeit!
Achtung, jetzt sollte man beachten, dass die Laufzeit des folgenden Codes Quadratisch ist und nicht linear, weil die Subscript-Methode wiederum linear ist!!

```swift
for i in name.count {
    print(name[i])
}
```

## Zusammenfassung

- Wie sind Strings gespeichert (z.B. ein Emoji)?
- Was ist die Implikation davon?

#learning unit#