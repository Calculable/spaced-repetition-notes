# NavigationStack
🧭

## Navigation Stack löst die NavigationView ab

> If your app has a minimum deployment target of iOS 16, iPadOS 16, macOS 13, tvOS 16, or watchOS 9, or later, transition away from using `NavigationView`- In its place, use `NavigationStack`and `NavigationSplitView` instances

## Bei 1-Spalten Layout (Stack)

Vorher:
```swift
NavigationView {

}.navigationViewStyle(.stack)
```

Nachher:

```swift
NavigationStack { /* content */}
```

Darin kann ich ganz normal navigation Links platzieren

## Bei 2- oder 3- Spaltenlayout

Siehe NavigationSplit View

## Zusammenfassung
- Wie macht man ein Ein-Spaltiges Layout?


#nur learning unit#