# Snap-Verhalten bei Scroll View
📜

##  Variante 1: eine View weiter-snappen
![][image-1]

```swift
ScrollView(.horizontal) {
    LazyHStack {
        ForEach(0..<20) { i in
            Rectangle()
                .fill(.blue)
                .frame(width: 150, height: 200)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.viewAligned)
```

## Variante 2: die ganze Bildschirmgrösse weiter-snappen
![][image-2]

```swift
ScrollView(.horizontal) {
    LazyHStack {
        ForEach(0..<20) { i in
            Rectangle()
                .fill(.blue)
                .frame(width: 150, height: 200)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.paging)
```

## Zusammenfassung
- Kein Code: Welche zwei Arte von Snap-Verhalten gibt es bei der ScrollView?

[image-1]:	assets/2024-02-11%2010.20.37.gif
[image-2]:	assets/2024-02-11%2010.21.13.gif

#learning unit#