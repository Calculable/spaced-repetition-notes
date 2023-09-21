# LLDB Commands
🧐
## p: print

Für die meisten Fälle

```swift
(MyCustomProject.MyCustomStruct) {
  first = "First"
  otherStruct = (first = "First", second = "Second")
  otherClass = (first = "First", second = "Second")
}
```

## po: print object description

Zusätzlich wird die Custom Object Description ausgegeben, wenn `CustomDebugStringConvertible` implementiert ist.

```swift
▿ MyCustomStruct
  - first : "First"
  ▿ otherStruct : MyOtherCustomStruct
    - first : "First"
    - second : "Second"
  ▿ otherClass : MyOtherCustomClass
    - first : "First"
    - second : "Second"
```

## v: frame variable

Es wird kein Code compiliert, so kann man sicher sein, dass man nichts verändert:

```swift
(CustomDebugStringConvertibleTest.MyCustomStruct) myCustomStruct = {
  first = "First"
  otherStruct = (first = "First", second = "Second")
  otherClass = (first = "First", second = "Second")
}
```

## vo: frame variable + object description

Gibt zusätulich  die object description aus

## Zusammenfassung
- Was ist der Unterschied zwischen `p`, `po` und `v`?

#learning unit#