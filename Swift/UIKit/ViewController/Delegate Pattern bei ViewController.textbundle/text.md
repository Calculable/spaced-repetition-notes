# Delegate Pattern bei ViewController
🍷

Oft gibt man beim erzeugen eines ViewControllers sich selbst als Delegate mit:

```swift
let testVC = storyboard?.instantiateViewController(identifier: "Test") as! TestViewController

testVC.delegate = self
```

##  Zusammenfassung
- Wer ist in der Regel das Delegate eines ViewControllers?

#learning unit#