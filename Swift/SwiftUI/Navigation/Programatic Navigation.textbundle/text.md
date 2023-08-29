# Programatic Navigation
🧭


## Codebeispiel

```swift
NavigationStack(path: $path) {
    List {
        NavigationLink("Purple", value: Color.purple)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Orange", value: Color.orange)
    }
    .navigationDestination(for: Color.self) { color in
        Text(color.description)
    }
}
```

Beachte: navigationDestination ist nicht an den NavigationStack gebunden sondern an die Liste

## Programmatic Navigation mit einem einfachen Boolean


```swift
.navigationDestination(isPresented: $isShowingXY) {
	//...
}
```

## Der Navigationspfad wird in einem Array gespeichert

Beachte: Path ist ein Array!!

Warum ist es ein Array: =\> Weil jede Zahl einen Wert tiefer in der Hierarchie markiert.

So kann man auch den Navigation Path serialisieren und wiederherstellen. 


## Wrapper

Hinweis: Es gibt auch einen Wrapper `NavigationPath` wenn man im NavigationArray unterschiedliche Datentypen benötigt. Details siehe hier: [How to use programmatic navigation in SwiftUI - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-use-programmatic-navigation-in-swiftui)

Man kann es auch serialisieren: [https://www.hackingwithswift.com/quick-start/swiftui/how-to-save-and-load-navigationstack-paths-using-codable][2]

## Verfügbarkeit

- Ab iOS 16

## Zusammenfassung
In einem NavigationStack eine Liste anzeigen. Mit einem Klick soll sich eine neue View öffnen. Es wird ein Pfad mit der Navigation gespeichert.








[2]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-save-and-load-navigationstack-paths-using-codable

#learning unit#