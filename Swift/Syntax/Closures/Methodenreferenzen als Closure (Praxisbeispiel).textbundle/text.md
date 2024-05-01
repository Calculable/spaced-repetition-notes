# Methodenreferenzen als Closure (Praxisbeispiel)
🔄


##  Frage: Was ist hier das Problem?

```swift
class MyClass {
	//...
	NotificationCenter.default.addObserver(
	  forName: .SomethingToObserverNotification, 
	  object: nil, 
	  queue: .main, 
	  using: handleNotification
	)
	//...
	func handleNotification() {

	}

	deinit {
    	NotificationCenter.default.removeObserver(self)
	}
}
```

## Antwort

- Der Code produziert einen Retain-Cycle!
- Wenn man eine Funktion als Closure übergibt, dann wird daduch `self` "strongly gecaptured":

![][image-1]

- deinit würde also nie aufgerufen

##  Lösung

```swift
NotificationCenter.default.addObserver(
  forName: .SomethingToObserverNotification,
  object: nil,
  queue: .main) { [weak self] notification in
    self?.handleNotification(notification)
}
```

##  Weiteres Praxisbeispiel

Auch das wäre ein Retain-Cycle:

```swift
class SomeModalViewController: UIViewController {
    var actionHandler: (() -> Void)?

    @IBAction func onTappedAction(_ sender: Any) {
        actionHandler?()
    }
}
```

```swift
let someModalVC = SomeModalViewController()
someModalVC.actionHandler = {
    someModalVC.dismiss(animated: true, completion: nil)
}
present(someModalVC, animated: true, completion: nil)
```

Lösung:

```swift
 let someModalVC = SomeModalViewController()
  someModalVC.actionHandler = { [weak someModalVC] in
      someModalVC?.dismiss(animated: true, completion: nil)
  }
  present(someModalVC, animated: true, completion: nil)
```


## Theorie

Siehe: [ulysses://x-callback-url/open?id=9u7XkbIABBkB0bS4VwQ-Zg][1]

##  Quelle
[https://doordash.engineering/2019/05/22/ios-memory-leaks-and-retain-cycle-detection-using-xcodes-memory-graph-debugger/][2]

[https://gist.github.com/chauvincent/b191414d54ba4cbb04614b1f85ac2e24][3]

##  Zusammenfassung
- Siehe Abschnitt "Was ist hier das Problem?"

[1]:	ulysses://x-callback-url/open?id=9u7XkbIABBkB0bS4VwQ-Zg
[2]:	https://doordash.engineering/2019/05/22/ios-memory-leaks-and-retain-cycle-detection-using-xcodes-memory-graph-debugger/
[3]:	https://gist.github.com/chauvincent/b191414d54ba4cbb04614b1f85ac2e24

[image-1]:	assets/DraggedImage.png

#learning unit#