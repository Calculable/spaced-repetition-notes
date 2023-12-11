# ViewController: loadView
🌅

Hier hat man die Möglichkeit, eine eigene View zu setzen:

```swift
class ViewController: UIViewController {

    override func loadView() {
        view = SharePromptView()
    }

}
```


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


Häufig ist das schöner, als stattdessen `viewDidLoad` zu überfrachten:

```swift
  override func viewDidLoad() {
    super.viewDidLoad()
	//background color
	//subviews hinzufügen
	//subview constraints festlegen....
  }
```
(Eigentlich ist das ja alles View-Code und nicht ViewController-Code)

## Zusammenfassung
- Was kann man in dieser Lifecycle Methode machen?


#learning unit#