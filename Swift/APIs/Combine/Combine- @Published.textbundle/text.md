# Combine: @Published
🔀

##  Konzept
- Damit kann man für eine Variable einen Publisher bekommen
- Beachte: Das braucht es nicht nur für SwiftUI
- Es ist somit sehr gut mit dem MVVM Pattern kompatibel, das View Model hat die @Published attribute (auch für UIKit sinnvoll)
- Seit iOS 13

##  Beispiel
Wenn man dieses Objekt hat:
```swift
final class FormViewModel {
    @Published var isSubmitAllowed: Bool = true
}
```

Dann bekommt man so einen Publisher:

```swift
subscriber = viewModel.$isSubmitAllowed
	.assign(to: \.isEnabled, on: submitButton)
```

## Object will Change
Wenn man `ObservableObject` erweitert, dann hat man zusätzlich auch den `objectWillChange` publisher:

```swift
class ObservableFormViewModel: ObservableObject {
	@Published var isSubmitAllowed: Bool = true
	@Published var username: String = ""
	@Published var password: String = ""
	var somethingElse: Int = 10
}

var form = ObservableFormViewModel()

let formSubscription = form.objectWillChange.sink { _ in
	print("Form changed: \(form.isSubmitAllowed) \"\(form.username)\" \"\(form.password)\"")
}
```


## Quelle

[https://www.avanderlee.com/swift/combine/][1]

##  Zusammenfassung
- Wie kann man `@Published` verwenden? (UIKit und SwiftUI)

[1]:	https://www.avanderlee.com/swift/combine/

#learning unit# #guide