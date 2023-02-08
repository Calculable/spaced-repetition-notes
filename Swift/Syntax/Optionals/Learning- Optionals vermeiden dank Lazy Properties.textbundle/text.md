# Learning: Optionals vermeiden dank Lazy Properties
🦥

Das ist oft bei UIKit sinnvoll, wo man ansonsten Implicity-Unwrapped-Optionals hat. Mit  Lazy Variables kann man das vermeiden:

```swift
lazy var collectionView = makeCollectionView()

func makeCollectionView() -> UICollectionView {
    //...
}
```

## Zusammenfassung
- Wie können Lazy Properties verwendet werden, um Optionals zu vermeiden?


#nur learning unit#