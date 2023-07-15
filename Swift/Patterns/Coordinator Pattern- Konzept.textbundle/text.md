# Coordinator Pattern: Konzept
👨🏻‍💼

## Konzept
- Der Coordinator kann sich um die Navigation kümmern (statt dass der ViewController das selbst macht)
- Vorteile: Gewisse Dinge lassen sich nun einfacher Programmieren, zum Beispiel wenn man mit einem Deep-Link zu einer gewissen View navigieren möchte, A/B-Testing etc.

## Übersicht
![][image-1]

## Codebeispiel
```swift
class Coordinator {

    var navigationController = UINavigationController()

    func showViewController() {
		//MoviesViewController instanzieren
        let initialViewController = ...

		//sich selbst als Coordinator setzen
        initialViewController.coordinator = self
	
		//anzeigen	
		navigationController.pushViewController(...)
    }
}
```

## Details

- [https://www.hackingwithswift.com/articles/71/how-to-use-the-coordinator-pattern-in-ios-apps][1]
- [https://www.hackingwithswift.com/articles/175/advanced-coordinator-pattern-tutorial-ios][2]
- [ulysses://x-callback-url/open?id=hUsnlwGMzjbBDabk7JO25w][3]

## Zusammenfassung
- Wozu ist der Coordinator gut?
- Wie hängen die Klassen zusammen (Übersichtsbild): App Delegate, Coordinator, NavigationController, ViewController(s)

[1]:	https://www.hackingwithswift.com/articles/71/how-to-use-the-coordinator-pattern-in-ios-apps
[2]:	https://www.hackingwithswift.com/articles/175/advanced-coordinator-pattern-tutorial-ios
[3]:	ulysses://x-callback-url/open?id=hUsnlwGMzjbBDabk7JO25w

[image-1]:	assets/DraggedImage.tiff

#learning unit#