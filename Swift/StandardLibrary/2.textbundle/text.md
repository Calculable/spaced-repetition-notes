# Häufige Array-Funktionen  ↩️

## First
```swift
let result = nums.first!
```


## First where
```swift
let result = nums.first(where: { $0 % 2 == 0 })!
```

## First Index

```swift
let result = nums.firstIndex(where: { $0 % 2 == 0 })!
```

## All Satisfy

```swift
let result = nums.allSatisfy { $0 < 10 }
```

## Contais

```swift
let result = nums.contains(2)
```

## Zusammenfassung
- First
- First Where
- First Index
- All Satisfy
- Contains