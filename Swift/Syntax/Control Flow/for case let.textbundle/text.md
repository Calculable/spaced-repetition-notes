# for case let
🔁

## Zweck

- Überspringt nil Werte

## Beispiel: Nil-Werte überspringen

```js
let names = ["Bill", nil, "Ted", nil]

for case let name? in names {
    print(name) //Bill und Ted
}
```

##  Optional Casts
so kann man über alle views loopen, die UILabels sind:

```js
for case let label as UILabel in view.subviews {
    print("Found a label with text \(label.text)")
}
```

##  Where

```js
for case let score in scores where score > 10 { ... }
```

##  Bestimmter Enum Case

```js
for case .text(let x) in hello {

}
```
##  Zusammenfassung
- Nil Werte Überspringen
- Optional Casts
- Where
- Bestimmter Enum Case

#learning unit#