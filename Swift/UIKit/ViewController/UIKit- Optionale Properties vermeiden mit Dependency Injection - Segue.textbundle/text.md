# UIKit: Optionale Properties vermeiden mit Dependency Injection - Segue
💉

## Siehe auch

UIKit: Optionale Properties vermeiden mit Dependency Injection - Storyboard

## Problem

In den ViewControllern hat man oft **implicitly unwrapped** optional Properties, weil man zwingend einen leeren Initializer braucht:


```swift
var title: String!
```

Beim erstellen des ViewControllers muss man vor iOS13 daran denken, diese Properties zu setzen:

```swift
func prepare (for segue: UIStoryboardSegue, sender: Any?) {
	if let viewController = segue.destination as ? DetailViewController {
        viewController.title = "injected detail"
    }
}
```

##  Nachteile

- Alles muss variable und public sein


## Lösung (seit iOS 13)


### Im Ziel-ViewController

Man macht einen Custom Initializer:

```swift
class DetailsViewController: UIViewController {
    
    @IBOutlet var label: UILabel!
    private var myCustomTitle: String
    
    init?(coder: NSCoder, title: String) {
        self.myCustomTitle = title
        super.init(coder: coder)
    }

    required init?(coder: NSCoder) {
        fatalError("You must create this view controller with a product.")
    }
    
    override func viewDidLoad() {
        label.text = myCustomTitle
        super.viewDidLoad()
        
    }
}
```


### Im ViewController, welcher den Übergang initiiert


Man zieht eine Verbindung vom bestehenden Segue in den Code:

![][image-1]

![][image-2]

```swift
@IBSegueAction func makeDetailsViewController(_ coder: NSCoder) -> DetailsViewController? {
	return DetailsViewController(coder: coder, title: "Custom Title")
}
```


=\> Die Funktion `override func prepare(for segue: UIStoryboardSegue, sender: Any?)` braucht man nicht mehr!


[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-23%20um%2008.03.11.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-03-23%20um%2008.07.21.png

#learning unit#