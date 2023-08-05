# Compiler-Direktive:  Betriebssytsem
⚙️

## Beispiel
```swift
#if os(iOS)
    // This code will only be compiled for iOS
    print("Running on iOS")
#elseif os(macOS)
    // This code will only be compiled for macOS
    print("Running on macOS")
#else
    // This code will be compiled for any other OS
    print("Running on another OS")
#endif
```

## Mögliche Werte

- `os(macOS)`
- `os(iOS)`
- `os(watchOS)`
- `os(tvOS)`
- `os(Linux)`
## Gegenteil

```swift
#if !os(tvOS)
```

##  Zusammenfassung
- Wie prüft man, ob man auf einer bestimmten Plattform läuft (zum Beispiel macOS)?

#learning unit#