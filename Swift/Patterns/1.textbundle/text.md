
# MVP 🏛️

![][image-1]

- Bei MVC hat man sehr grosse ViewController
- Bei MVP kann die Logik in einen Presenter verschoben werden
- Presenter ist einfacher zu testen


```swift
protocol PresenterView: class {
    func updateLabel()
}
```

```swift
import UIKit
class ViewController: UIViewController, PresenterView {
	lazy var presenter = Presenter(with: self) //beachte - hier gibt man self mit
	@IBOutlet weak var changeTextLabel: UILabel!
	
	override func viewDidLoad() {
	    super.viewDidLoad()
	}
	
	@IBAction func tapMeButton(_ sender: Any) {
	    presenter.buttonTapped()
	}

   func updateLabel() {
   		changeTextLabel.text = "I have been changed!"  
   }
}
```


```swift
import Foundation

class Presenter {
	weak var view: PresenterView?

	// Pass something that conforms to PresenterView
	init(with view: PresenterView) {
	    self.view = view
	}

	var timesTapped = 0
	func buttonTapped() {
    	timesTapped += 1
    	if timesTapped >= 5 {
    	self.view?.updateLabel()
	}	
}

```

##  Zusammenfassung
- Rollen
- Zusammenspiel

[image-1]:	https://miro.medium.com/max/640/1*Yf9H3RWc9pdcnxxco_dTqQ.webp

#nur learning unit#