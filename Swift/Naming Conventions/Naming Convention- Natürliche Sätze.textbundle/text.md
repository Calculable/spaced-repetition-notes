# Naming Convention: Natürliche Sätze
💬

## Gute Beispiele

```swift
x.insert(y, at: z)
x.subViews(havingColor: y)
x.capitalizingNouns()
```

## Ausnahmen

- Konstruktoren und Factory-Methoden

Wenn man mehrere Argumente hat, muss es nach 1-2 Argumenten nicht mehr unbedingt natürlich klingen:

```swift
Audio.Unit.instantiate(with: description, options: [...])
```

## Schlechte Beispiele

```swift
x.insert(y, position: z)
x.subViews(color: y)
x.nounCapitalize()
```


## Zusammenfassung
- Wie macht man Funktionen, die wie natürliche Sätze klingen
- Welche Ausnahmen gibt es?


#nur learning unit# #learning unit#