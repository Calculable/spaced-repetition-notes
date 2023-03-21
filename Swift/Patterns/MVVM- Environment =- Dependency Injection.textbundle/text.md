# MVVM: Environment  =\> Dependency Injection
💉

## ViewModels können nicht auf @Environment oder @EnvironmentObject zugreifen

Deshalb müssen solche Objekte im Initializer empfangen werden:

```swift
let dataController: DataController

init(dataController: DataController) {
    self.dataController = dataController
}
```

## Dependency Injection auch für die View

Wenn man ein ViewModel hat, wird oft auch nicht in der View auf `@Environment` oder `@EnvironmentObject` zugegriffen, sondern auch hier Dependency-Injection verwendet:

```swift
init(dataController: DataController) {
    let viewModel = ViewModel(dataController: dataController, showClosedProjects: true)
    _viewModel = StateObject(wrappedValue: viewModel)
}
```

Stattdessen verwendet eine darüberliegende View dann `@Environment` oder `@EnvironmentObject`

## Zusammenfassung
- Wie hat man im ViewModel Zugriff auf `@Environment`-Variabeln?

#learning unit#