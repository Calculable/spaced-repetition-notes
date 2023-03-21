# Unterschied zwischen „()“ und „Void“
🤷‍♂️

## Frage

Manchmal sieht man einen Funktionstypen so:

```swift
() -> ()
func someFunc() {}
func someFunc() -> () {}
```

und manchmal so:

```swift
() -> Void
func someFunc() -> Void {}
```


##  Antwort

Es ist das gleiche:

```swift
public typealias Void = ()
```

genau genommen hat es sich um ein leeres Tupel

#learning unit#