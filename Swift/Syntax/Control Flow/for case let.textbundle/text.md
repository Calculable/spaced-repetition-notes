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

##  Weiteres Beispiel
so kann man über alle views loopen, die UILabels sind:

```js
for case let label as UILabel in view.subviews {
    print("Found a label with text \(label.text)")
}
```

##  Weiteres Beispiel

```js
for case let score in scores where score > 10 { ... }
```

##  Weiteres Beispiel mit Enum Case

```js
for case .text(let x) in hello {

}
```
##  Zusammenfassung
- Zweck
- Syntax

#learning unit#