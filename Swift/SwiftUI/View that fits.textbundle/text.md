# View that fits
↔️

## Codebeispiel

Je nach verfügbarem Platz wählt das System ein Layout:

```swift
ViewThatFits {
    HStack {
        Text("The rain")
        Text("in Spain")
        Text("falls mainly")
        Text("on the Spaniards")
    }

    VStack {
        Text("The rain")
        Text("in Spain")
        Text("falls mainly")
        Text("on the Spaniards")
    }
}
.font(.title)
```


Ideal, wenn man die App für verschiedene Gerätegrössen baut

## Wie wird entschieden, welche Variante gewählt wird?

Text in SwiftUI prefers to sit on one line, and by default `ViewThatFits` will prefer to avoid layouts the cause text to wrap.

## Zusammenfassung
- Code / Zweck


#nur learning unit#