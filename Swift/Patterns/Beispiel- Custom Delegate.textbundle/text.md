# Beispiel: Custom Delegate
📜
```swift
protocol CustomDelegate: AnyObject {
    func didFinishTask(sender: TaskManager, message: String)
}
```

Beachte: AnyObject wird verwendet. So kann man später wo das Delegate benötigt wird `weak` verwenden:


```swift
weak var delegate: CustomDelegate?
```


## Zusammenfassung
- Was muss man speziell beachten?

#learning unit#