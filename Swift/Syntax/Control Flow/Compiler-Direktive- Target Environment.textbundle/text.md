# Compiler-Direktive: Target Environment
⚙️

## Beispiele

```swift
#if targetEnvironment(macCatalyst)
    print("UIKit running on macOS")
#else
    print("Your regular code")
#endif 
```

```swift
#if targetEnvironment(simulator)
    // Code specific to Simulator
#else
    // Code for all other environments
#endif
```

- Nicht mit dem Betriebssystem verwechseln

##  Zusammenfassung
- Code nur auf dem Simulator oder Unter macCatalyst ausführen




#learning unit#