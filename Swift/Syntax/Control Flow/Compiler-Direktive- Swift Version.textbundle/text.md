# Compiler-Direktive: Swift Version
⚙️

```swift
#if swift(>=5.7)
print("Running Swift 5.7 or later")
#else
print("...)
#endif
```

##  Anwendungsfälle
- Man will eine Library bauen, welche mehr als eine Swift Version unterstützt
- Man will mit neuen Swift-Features experimentieren

##  Zusammenfassung
- Code nur ab einer bestimmten SwiftVersion ausführen (z.B. ab Swift 5.7)

#learning unit#