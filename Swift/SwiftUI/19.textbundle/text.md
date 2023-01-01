# EnvironmentObject 🌳
::19::

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

## Zusammenfassung
- Wie erstellt man ein EnvironmentObject (Annotation) und gibt dieses an die Subviews weiter?
- Wie greifen die Subviews auf das Environment-Objekt z