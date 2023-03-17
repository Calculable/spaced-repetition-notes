# print vs. debugPrint CustomStringConvertible vs. CustomDebugStringConvertible)
🖨️


## Unterschiede
- Bei `debugPrint` werden oft weitere Informationen ausgegeben
- Ausserdem wandelt `debugPrint` Ausdrücke wie `\t` oder `\n` nicht um.

## Verhalten überschreiben
- Man kann eine eigene `description` erstellen, wenn man `CustomStringConvertible` implementiert
- Man kann eine eigene `debugDescription` erstellen, wenn man `CustomDebugStringConvertible`  implementiert.

## Beispiel
```swift
print(1..5) //prints 1..5
debugPrint(1..5) //prints CountableClosedRange(1..5)
```

## Zusammenfassung
- Wie verhält sich `debugPrint` und `print` unterschiedlich?
- Welche Protokolle werden im Hintergrund verwendet?



#nur learning unit# #learning unit#