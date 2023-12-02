
# MVP
🏛️

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

## Unterschied zwischen MVP und MVVM

- Bei MVP geht es darum, dass der Presenter den UI Status enthält und die Transformationen macht, damit dies im UI dargestellt werden kann.
- MVVM ist eigentlich die gleiche Idee, fügt dem ganzen aber noch data bindings hinzu, so dass UI-Änderungen automatisch im ViewModel reflektiert werden und Änderungen im ViewModel automatisch im UI.


##  Zusammenfassung
- Rollen / Zusammenspiel: Was geschieht bei einem Klick=
- Unterschied zu MVVM

[image-1]:	assets/MVP.drawio.png

#learning unit#