# OS Version Check
⚙️

##  Beispiel: 
```swift
if #available(iOS 10, macOS 10.12, *) {
    // Use iOS 10 APIs on iOS, and use macOS 10.12 APIs on macOS
} else {
    // Fall back to earlier iOS and macOS APIs
}
```

## Für was steht der Stern \*?
- Der `*` bedeutet: Bei allen anderen Platformen (und zukünftigen Platformen) ist die Bedingung erfüllt. Ansonsten nicht.
- Der Stern ist verpflichtend.

## Gegenteil

Since Swift 2.6 kann man auch das schreiben.

```swift
if #unavailable(iOS 15) {
    // Code to make iOS 14 and earlier work correctly
}
```

Beachte: Hier braucht es keinen Stern


##  Warum ist es keine Compiler direktive?
- Achtung: Dies ist ein Runtime-Check und nicht eine Compiler-Direktive!
- Denn ansonsten müsste man ja für jede OS Version einen eigeen Build machen

## Zusammenfassung
- IF-Statement, welches die OS-Version prüft
- Beispiel: Code soll ab iOS 10 und macOS 10.12 laufen
- Warum ist das keine Compiler Direktive

#learning unit#