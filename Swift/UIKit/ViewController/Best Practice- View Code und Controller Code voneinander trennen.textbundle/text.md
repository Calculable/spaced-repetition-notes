# Best Practice: View Code und Controller Code voneinander trennen
✂️

## Problem / Schlechtes Beispiel
Man sollte den Code im `viewDidLoad` nicht überfrachten so wie hier:

```swift
    override func viewDidLoad() {
        super.viewDidLoad()
        
		backgroundColor = UIColor(white: 0.9, alpha: 1)

		let stackView = UIStackView()
		stackView.translatesAutoresizingMaskIntoConstraints = false
		stackView.spacing = 10
		view.addSubview(stackView)

		stackView.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor).isActive = true
		stackView.leadingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.leadingAnchor).isActive = true
		stackView.trailingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.trailingAnchor).isActive = true
		stackView.axis = .vertical

		let notice = UILabel()
		notice.numberOfLines = 0
		notice.text = "Your child has attempted to share the following photo from the camera:"
		stackView.addArrangedSubview(notice)

    }
```


## Warum ist es schlecht?

- Das ist alles View Code und nicht Controller Code (auch nicht ViewController code)

## Lösung

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

Beachte, wie die neue `shareView` dem bereits vorhandenen Property `shareView` zugewiesen wird.


## Zusammenfassung
Wie kann man den View Code innerhalb von `viewDidLoad` auslagern?


#nur learning unit# #learning unit#