# Wann verwendet man Binding und wann nicht
💵

## Beispiel
Warum muss man hier ein `$` mitgeben:

```swift
.alert("abcd", isPresented: $xy) { //
```

aber hier nicht:

```swift
.onChange(of: xy) { //
```

## Antwort
=\> Weil der Alert den Wert ja verändert und onChange nicht

##  Zusammenfassung
Warum braucht es bei onChange kein Dollar-Zeichen?

#learning unit#