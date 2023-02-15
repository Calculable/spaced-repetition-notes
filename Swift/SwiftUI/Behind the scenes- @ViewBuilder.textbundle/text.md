# Behind the scenes: @ViewBuilder
👷‍♂️

## Wie wird der ViewBuilder verwendet?

Damit kann man mehrere Views zu einer View machen:

```swift
@ViewBuilder func create() -> some View {
    Text("1")
    Text("2")
    Text("3")
}
```

## Wie funktioniert der ViewBuilder im Hintergrund?

- Es ist einfach ein ganz normaler `ResultBuilder`. 
- Der ResultBuilder erstellt im Hintergrund eine `TupleView`-
- `TupleViews` können natürlich ineinander verschachtelt sein


## Zusammenfassung
- Wie funktioniert ein `@ViewBuilder` im Hintergrund?


#nur learning unit#