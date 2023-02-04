# Inlinable 🖨️

## Was ist Inlinable?
- Mit dem `Inlinable`-Keyword sagt man dem Compiler, dass er den Inhalt der Funktion beim builden überall dort einsetzen kann, wo sonst der Aufruf wäre

## Beispiel

```swift
@inlinable
func contains(_ element: Element) -> Bool {
    array.contains(element)
}
```

## Vorteil
- Perfomance Gewinn

## Nachteil
- Der Build benötigt mehr Speicherplatz

> you’re also making a commitment that the underlying implementation won’t change. Think about it: if you ship an enhanced version of your inlinable function later on, existing code that uses it won’t be able to use it – they’ll have their own version of the original function, which was copied directly in to their binary.

## Zusammenfassung
- Bedeutung
- Vorteil
- Nachteil


#nur learning unit#