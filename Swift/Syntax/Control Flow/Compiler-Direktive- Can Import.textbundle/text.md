#  Compiler-Direktive: Can Import
⚙️

##  Codebeispiel

```swift
#if canImport(UIKit)
// iOS, tvOS, and watchOS – use UIColor
#elseif canImport(AppKit)
// macOS – use NSColor
#else
// all other platforms – use a custom color object
#endif
```

> Before  `canImport()`  was available we need to use  `#if os(macOS)`  instead, like this:

```swift
#if os(iOS) || os(tvOS) || os(watchOS)
// use UIColor
#else
// use NSColor
#endif
```



##  Zusammenfassung
- Beispiel: Code nur ausführen, wenn UIKit verfügbar ist

#learning unit#