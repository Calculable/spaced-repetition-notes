# Best Practice: View Code und Controller Code voneinander trennen
✂️

## Problem / Schlechtes Beispiel
Man sollte den Code im `viewDidLoad` nicht überfrachten so wie hier:

```swift
  override func viewDidLoad() {
    super.viewDidLoad()
	//background color
	//subviews hinzufügen
	//subview constraints festlegen....
  }
```


## Warum ist es schlecht?

- Das ist alles View Code und nicht Controller Code (auch nicht ViewController code)

## Lösung

Jetzt sieht der ViewController schön aufgeräumt aus.

```swift
class ViewController: UIViewController {
    var shareView = SharePromptView()

    override func loadView() {
        view = shareView
    }

    override func viewDidLoad() {
        super.viewDidLoad()
    }
}
```


Man kann diese Dinge in eine UI View auslagern:

```swift
class SharePromptView: UIView {
    override init(frame: CGRect) {
        super.init(frame: frame)
        createSubviews()
    }

    required init?(coder aDecoder: NSCoder) {
        super.init(coder: aDecoder)
        createSubviews()
    }

    func createSubviews() {
        // all the layout code from above
    }
}
```


Beachte, wie die neue `shareView` dem bereits vorhandenen Property `shareView` zugewiesen wird.


## Zusammenfassung
- Wie kann man den View Code innerhalb von `viewDidLoad` auslagern?
- In welcher Methode?
- 


#learning unit#