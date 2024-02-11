# AttributedString
💬

So kann man mehrere Strings miteinander kombinieren mit unterschiedlichen Styling:

```swift
struct ContentView: View {

    var message1: AttributedString {
        var result = AttributedString("Hello")
        result.font = .largeTitle
        result.foregroundColor = .white //neu: foregroundStyle
        result.backgroundColor = .red //neu: backgroundStyle
        return result
    }

    var message2: AttributedString {
        var result = AttributedString("World!")
        result.font = .largeTitle
        result.foregroundColor = .white //neu: foregroundStyle
        result.backgroundColor = .blue //neu: backgroundStyle
        return result
    }

    var body: some View {
        Text(message1 + message2)
    }
}
```

Hinweis: Wahrscheinlich wird in diesem Codebeispiel das Computed Property verwendet, weil ansonsten der Rückgabewert eine Background Color ist und nicht ein Attributed String...

Beachte: Die Syntax ist nicht deklarativ!

## Wo kann es besonders sinnvoll sein?

Zum Beispiel für Accessibility, damit man nicht immer die gleiche Information wiederholen muss

```swift
    var message: AttributedString {
        var password = AttributedString("abCayer-muQai")
        password.accessibilitySpeechSpellsOutCharacters = true
        return "Your password is: " + password
    }

    var body: some View {
        Text(message)
    }
```

## Was kann man sonst noch machen?
- Einzelne Buchstaben indivisuell anpassen (z.B. rotation etc.)
- Links machen

## Alternative

Man kann Text auch so kombinieren:

```swift
Text("SwiftUI ")
    .font(.largeTitle)
+ Text("is ")
    .font(.headline)
+ Text("awesome")
    .font(.footnote)
```

## Quelle
Quelle: [How to add advanced text styling using AttributedString - a free SwiftUI by Example tutorial (hackingwithswift.com)][1]

Weiterführende Informationen: [https://www.hackingwithswift.com/plus/hacking-with-swift-live-2021/finishing-up][2]

## Warnung

> **Warning:**  If you explore the API using Xcode’s autocomplete, you’ll see all sorts of options that look like they ought to work but in fact do nothing at all.

## Zusammenfassung
- (kein Code)
- Wie kombiniert man unterschiedliche Stylings in einem Text?
- Anwendungsbeispiel Accessibility?
- Alternative


[1]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-add-advanced-text-styling-using-attributedstring
[2]:	https://www.hackingwithswift.com/plus/hacking-with-swift-live-2021/finishing-up

#learning unit#