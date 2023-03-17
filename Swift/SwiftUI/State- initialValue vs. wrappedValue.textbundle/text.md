# State: initialValue vs. wrappedValue
🎭

Es gibt inhaltlich keinen Unterschied zwischen diesen beiden Varianten:

```swift
_title = State(wrappedValue: item.itemTitle)
```

```swift
_title = State(initialValue: item.itemTitle)
```

>  `initialValue`  is “more idiomatic and clear” – we’re being explicit that this is the initial value, whereas “wrapped value” is there because Swift requires it.

## Zusammenfassung
Was ist der Unterschied zwischen State(initialValue: ...) und State(wrappedValue: ...)?


#nur learning unit# #learning unit#