# ViewController initialisieren
🏁

## Codebeispiel

```swift
class ViewController: UITableViewController {
    
    var pictures: [String] = []

	//loadView() gets called before viewDidLoad()
	//braucht man nicht, wenn es vom Storyboard geladen wird
	override func loadView() {
		//...
		//Hier könnte man die eigentliche view noch zuweisen
		//view = ...
	}

    override func viewDidLoad() {
        super.viewDidLoad()
        
       	//load data
		pictures = ...
    }

}
```


## Zusammenfassung
- Welche zwei Funktionen spielen eine Rolle, wann braucht man es

#learning unit#