# EnvironmentObject
🌳

##  EnvironmentObjects sind ObservableObjects
- Environment Object nutzen das gleiche `ObservableObject` Protokoll. Man kann somit die Properties mit `@Published` annotieren. 
- Funktioniert nur mit Klassen

## EnvironmentObject platzieren

```swift
@StateObject var user = User()
```

```swift
VStack {
    EditView()
    DisplayView()
}
.environmentObject(user)
```

## EnvironmentObject auslesen

```swift
@EnvironmentObject var user: User
```


## Unterschied zwischen Environment und EnvironmentObject

### @EnvironmentObject (ObservableObject Class)

> Use  `@EnvironmentObject`  when it would be too cumbersome to pass an observable object through all the initializers of all your view’s ancestors.

```swift
@EnvironmentObject var veggieFetcher: VegetableFetcher
```

### @Environment

> Use  `@Environment`  when your view is dependent on a type that cannot conform to ObservableObject (zum Beispiel Structs, Closures, Ein Protokolltyp...)

```
@Environment(\.theme) var theme: Theme
```

Beachte: Im Vergleich zu `@EnvironmentObject` darf man hier unterschiedliche Typen haben.

## Environment im Initializer

Im Initializer hat man Zugriff auf die Environment-Variabeln:

```swift
@Environment(\.accessibilityEnabled) var accessibilityEnabled
    
init() {
	if accessibilityEnabled {
		print("Accessibility is enabled!")
	}
}
```

## Zusammenfassung
- Wie erstellt man ein EnvironmentObject (Annotation) und gibt dieses an die Subviews weiter?
- Wie greifen die Subviews auf das Environment-Objekt zugreifen
- Unterschied Environment und Environment-Object

#learning unit#