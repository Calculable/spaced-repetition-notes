# View that fits
↔️

## Codebeispiel

Je nach verfügbarem Platz wählt das System ein Layout (von oben nach unten)

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

- Es wird das erste Layout genommen, das Platz hat

> Text in SwiftUI prefers to sit on one line, and by default `ViewThatFits` will prefer to avoid layouts the cause text to wrap.

## Beispiel

```swift
ViewThatFits(in: .vertical) {
    Text(veryLongText)

    ScrollView {
        Text(veryLongText)
    }
}
```

=\> Da wir uns nur für `vertical` interessieren, akzeptiert SwiftUI auch das obere Layout, weil es den Text umbrechen kann. Wenn jedoch der Vertikale Platz nicht mehr ausreicht (also der Text über den ganzen Bildschirm geht), wird eine Scroll View verwendet

## Zusammenfassung
- Code / Zweck


#learning unit#