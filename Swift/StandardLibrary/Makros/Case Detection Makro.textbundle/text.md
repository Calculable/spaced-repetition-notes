# Case Detection Makro
🤖

## Vorher

```swift
enum Path {
    case relative(String)
    case absolute(String)

    var isAbsolute: Bool {
        if case .absolute = self { true }
        else { false }
    }

    var isRelative: Bool {
        if case .relative = self { true }
        else { false }
    }
}
```

##  Nachher

```swift
@CaseDetection
enum Path {
    case relative(String)
    case absolute(String)
}

let absPaths = paths.filter { $0.isAbsolute }
```

##  Zusammenfassung
- Man will für ein Enum `Path` die Computed Properties `isAbsolute` und `isRelative` generieren: Benötigte Annotation 

#Swift5.9# #learning unit#