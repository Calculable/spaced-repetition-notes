# ViewController: View Laden
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
- Funktion um die View zu laden
- Funktion, um die View mit Inhalt zu befüllen

#learning unit#