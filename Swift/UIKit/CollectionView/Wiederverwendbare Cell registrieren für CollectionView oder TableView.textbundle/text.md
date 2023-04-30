# Wiederverwendbare Cell registrieren für CollectionView oder TableView
♻️

##  Variante 1: über das Storyboard

### Registrieren
- Prototyp Cell definieren
- Reuse Identifier setzen

### Dequeue
- Siehe Variante 2

## Variante 2: Programmatisch

### Registrieren
Innerhalb von `viewDidLoad`:

```swift
tableView.register(UITableViewCell.self, forCellReuseIdentifier: "DefaultCell")
```

### Dequeue
```swift
    let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "MyCollectionViewCell", for: indexPath) as! MyCollectionViewCell
    // Configure the cell with data
    return cell
```

## Variante 3: Seit iOS 14

### Registrieren
Innerhalb von `viewDidLoad`:

```swift
let cellRegistration = UICollectionView.CellRegistration {(cell: UICollectionViewListCell, indexPath: IndexPath, itemIdentifier: MyModel.ID) in

	//let reminder = Reminder.sampleData[indexPath.item] //beachte: .item
	reminder(withId: id) //custom function
	var contentConfiguration = cell.defaultContentConfiguration()
	contentConfiguration.text = reminder.title
	cell.contentConfiguration = contentConfiguration
}
```

Der Typ wäre hier: `UICollectionView.CellRegistration<UICollectionViewListCell, MyModel.ID>`
 
Achtung - das ist nicht eine Funktion, die nur einmal aufgerufen wird. Diese Funktion wird immer aufgerufen, wenn es eine Zelle darzustellen gibt! 


::Beachte: Man kann mit `indexPath.item` den gewünschten Reminder auslesen, aber vermutlich macht es mehr Sinn, stattdessen die übergebene ID zu verwenden::

> UICollectionView.CellRegistration is a new and more powerful way to register cells with a collection view. It allows you to define the cell configuration logic directly in the registration closure, instead of using a separate data source or delegate object. This can make your code more concise and easier to read.

Hinweis: `UICollectionViewListCell` ist eine vordefiniere Cell (siehe auch separates Kapitel, keine Learning Unit). Man kann aber auch eine eigene Cell erstellen, wenn man von UICollectionViewCell erbt.

Man kann auf indexPath
### Dequeue (Beispiel mit Data Source)
```swift
dataSource = DataSource(collectionView: collectionView) {(collectionView: UICollectionView, indexPath: IndexPath, itemIdentifier: String) in

	return collectionView.dequeueConfiguredReusableCell(using: cellRegistration, for: indexPath, item: itemIdentifier)
}
```

Hinweis: Der itemIdentifier ist von uns definiert, wenn wir einen Snapshot erstellen. Siehe auf `indexPath.section` zugreifen, um den Index der Section zu erhalten, wenn man mehrere hat. 


## Zusammenfassung
- Welche 3 Varianten gibt es, und wie unterscheiden sie sich?

#learning unit#