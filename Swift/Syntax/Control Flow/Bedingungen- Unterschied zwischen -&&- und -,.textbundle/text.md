# Bedingungen: Unterschied zwischen "&&" und ","
💡

 Mit `,` kann man auf zugewiesene Variabeln aus der Vorbedingung zugreifen, bei `&&` hingegen nicht.


Beispiel:

```swift
//funktioniert
if case MyEnum(let value) = x, value.isY {...}

//funktioniert nicht
if case MyEnum(let value) = x && value.isY {...}
```


```swift
//funktioniert
if let value = x, value.isY {...}

//funktioniert nicht
if let value = x && value.isY {...}
```


##  Zusammenfassung
- Was ist der Unterschied




#learning unit#