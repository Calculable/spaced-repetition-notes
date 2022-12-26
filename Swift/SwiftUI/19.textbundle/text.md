# EnvironmentObject
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
