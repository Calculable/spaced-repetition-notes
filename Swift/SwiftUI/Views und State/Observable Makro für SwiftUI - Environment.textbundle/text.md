# Observable Makro für SwiftUI - Environment
🌳

##  Verfügbar machen
```swift
ContentView()
	.environment(account)
```

=\> Man kann auch Custom Keys anwenden. Standartmässig wird der Typ als Key verwendet.

## Zugriff

```swift
@Environment(Account.self) var account
```

## Environment / Environment Object

Neu gibt es keine Unterscheidung mehr zwischen Environment und EnvironmentObject 

##  Hinweis
Aktuell sind Environment noch nicht Bindable. Siehe: [https://stackoverflow.com/questions/76546200/how-to-use-swift-macros-with-observable-and-environment][1]

## Zusammenfassung
- Wie macht man ein Environment Objekt verfügbar?
- Wie greift man auf das Environment-Objekt zu?


[1]:	https://stackoverflow.com/questions/76546200/how-to-use-swift-macros-with-observable-and-environment

#learning unit#