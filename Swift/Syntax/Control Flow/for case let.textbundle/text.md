# for case let
🔁

## Zweck

- Überspringt nil Werte

## Code: Nil-Werte überspringen

```js
let names = ["Bill", nil, "Ted", nil]

for case let name? in names {
    print(name) //Bill und Ted
}
```

so kann man über alle views loopen, die UILabels sind:

```js
for case let label as UILabel in view.subviews {
    print("Found a label with text \(label.text)")
}
```

## Code: Wenn man nur auf einen Switch-Type reagieren möchte

> The Swift If-Case-Let syntax is a convenient shortcut to avoid a full switch statement when you only want to match a single case



##  Zusammenfassung
- Zweck (2)
- Syntax

#learning unit#