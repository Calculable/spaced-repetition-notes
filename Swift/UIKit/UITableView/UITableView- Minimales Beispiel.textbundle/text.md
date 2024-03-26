# UITableView: Minimales Beispiel
🍽️

![][image-1]

```swift
import UIKit

class MyTableViewController: UITableViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
		//1. Zelle Registrieren
        tableView.register(UITableViewCell.self, forCellReuseIdentifier: "cell")
    }

    // 2. Anzahl Zellen zurückgeben
    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return 5
    }

	// 3. Zelle "dequen" und anzeigen
    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
        cell.textLabel?.text = "This is cell \(indexPath)"
        return cell
    }
}
```


##  Re-Use Prinzip

=\> Die Cell’s werden wiederverwendet um Ressourcen zu sparen
Beachte: Man gibt auch einen Index mit (das wird intern benötigt)

![][image-2]

## Erweiterungsmöglichkeiten
- Siehe Folgeabschnitte
	- Custom Cell
	- Default Cell Konfigurieren
	- Data Soruce etc.

##  Zusammenfassung
- Welche drei Dinge muss eine Table View machen (ohne Code, ohne separate Data Source)

[image-1]:	assets/Simulator%20Screenshot%20-%20iPhone%2015%20Pro%20-%202023-12-06%20at%2008.43.05.png
[image-2]:	assets/Bildschirmfoto%202021-09-03%20um%2014.47.45.png

#learning unit#