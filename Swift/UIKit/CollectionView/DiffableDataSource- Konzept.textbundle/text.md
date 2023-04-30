# DiffableDataSource: Konzept
⛲️

## Zweck

- Das Protokoll sagt der Collection View, welche und wie viele Zellen angezeigt werden sollen
- Unterschied: Statt nur zu sagen, wie viele Items man anzeigen möchte, sagt man konkret, welche Sections und Items man anzeigen möchte.
- Früher gab es nur `UICollectionViewDataSource`, heute gibt es auch `UICollectionViewDiffableDataSource`
- Bei DiffableDataSource können die Änderungen animiert angezeigt werden

## Code

### Typealias
```swift
 typealias DataSource = UICollectionViewDiffableDataSource<Int, MyModel.ID>
```

Beachte: Hier ist jede Section einfach ein Int. es kann jedoch ein beliebiger Typ sein (zum Beispiel wenn man für jede Section einen Header anzeigen will)

### Der UICollectionViewController hat ein Property

```swift
var dataSource: DataSource!
```

Dieses wird dann im `viewDidLoad` gesetzt.

### Data Source erzeugen 

![][image-1]

Man kann für den itemIdentifier zum Beispiel auch `MyModel.ID` verwenden, wenn dieses Identifiable ist.

Um die Reusable Cell aufzusetzen: Siehe separates Kapitel

### Daten übergeben

Das soll jedes mal gemacht werden, wenn sich etwas an der Data-Source ändert:

```swift
 typealias Snapshot = NSDiffableDataSourceSnapshot<Int, MyModel.ID>
```

```swift
var snapshot = Snapshot()
snapshot.appendSections([0]) //Sections interessieren uns hier nicht, aber wir brauchen zwingend eine.
snapshot.appendItems(myObjects.map {$0.id}) //Hier könnte man auch die gewünschte Section angeben. Standartmässig wird es einfach zur letzten Section. Hier übergibt man die Identifier und nicht zwingend das ganze Objekt
dataSource.apply(snapshot, animatingDifferences: true)
```

Beachte: Als Items werden Identifier übergeben. Beim Konfigurieren der Zelle kann man dann selbst auswählen, wie man damit umgehen möchte. 

### Bestimmte Einträge neu laden

Beachte: Die Diffs werden im gezeigten Beispiel nur anhand der IDs erzeugt (Hinzufügen und Löschen von ganzen Einträgen funktioniert also, aber nicht anpassen für einzelne Einträge). Wenn sich explizit etwas in einem Eintrag verändert hat, ruft man folgendes auf:

```swift
snapshot.reloadItems([id1, id2])
//apply snapshot
```

## Zusammenfassung
- Zweck
- Konzept (Grob, nicht genauer Code)
	- Wo wird die Data Source gespeichert
	- Wo wird die Zelle erzeugt
	- Wie werden Daten übergeben
	- Wie werden Daten neu geladen?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-04-23%20um%2010.45.39.png

#learning unit#