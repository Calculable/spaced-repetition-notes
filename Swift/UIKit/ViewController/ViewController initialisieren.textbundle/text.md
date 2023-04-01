# ViewController initialisieren
🏁

## Codebeispiel

```swift
class ViewController: UITableViewController {
    
    var pictures: [String] = []

	//loadView() gets called before viewDidLoad()
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
- Welche zwei Funktionen spielen eine Rolle

#learning unit#