# In eine Loop durch alle Objekte iterieren, die einen bestimmten Typ haben
🔁

##  Code: Mit Optional Casts
so kann man über alle views loopen, die UILabels sind:

```js
for case let label as UILabel in view.subviews {
    print("Found a label with text \(label.text)")
}
```

## Zusammenfassung
- Syntax

#learning unit#