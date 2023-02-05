# Programatic Navigation  🧭

## Hinweis

- Ab iOS 16

## Der Navigationspfad wird in einem Array gespeichert

Beachte: Path ist ein Array!!

Warum ist es ein Array: =\> Weil jede Zahl einen Wert tiefer in der Hierarchie markiert.

So kann man auch den Navigation Path serialisieren und wiederherstellen. 


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


## Wrapper

Hinweis: Es gibt auch einen Wrapper `NavigationPath` wenn man im NavigationArray unterschiedliche Datentypen benötigt. Details siehe hier: [How to use programmatic navigation in SwiftUI - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-use-programmatic-navigation-in-swiftui)

## Zusammenfassung
- Codebeispiel, Zweck




#nur learning unit#