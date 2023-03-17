# Best Practice: View aufteilen
✂️

## Variante 1: als eigenes View Struct
- Meistens zu bevorzugen

## Variante 2: Computed Property
Wenn man sehr viele Informationen mitgeben müsste, wenn man die View aufteilt, ist es manchmal besser, einen Teil der View in ein Computed Property auszulagern, anstatt ein neues View-Struct zu erstellen


```swift
var projectsList: some View {
    // paste your code here
}
```

## Variante 3: Als Funktion

Falls nötig kann man sogar Funktionen machen:

```swift
func colorButton(for item: String) -> some View {
    // paste your code here
}
```

## Zusammenfassung
- Welche drei Varianten gibt es, um eine View aufzuteilen?


#nur learning unit# #learning unit#