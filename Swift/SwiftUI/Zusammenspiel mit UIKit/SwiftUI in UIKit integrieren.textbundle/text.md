# SwiftUI in UIKit integrieren
🎁

## UIHostingController erstellen

Mit **UIHostingController**

```swift
let swiftUIView = SampleSwiftUIView()
let hostingController = UIHostingController(rootView: swiftUIView)
```

##  UIHostingController verwenden
Jetzt kann man den Controller wie ein ganz normaler UIKit Controller verwenden:

```swift
addChild(hostingController)
hostingController.view.translatesAutoresizingMaskIntoConstraints = false
view.addSubview(hostingController.view)
//(layout constraints für view definieren)
hostingController.didMove(toParent: self)
```

Oder man verwendet einfach die View:

```swift
addSubview(hostingController.view)
hostingController.view.translatesAutoresizingMaskIntoConstraints = false
//(layout constraints für view definieren)
```

[https://blog.devgenius.io/combining-swiftui-and-uikit-a-guide-to-interoperability-4b458ee75b61][1]


## Zusammenfassung
- Mit welcher Wrapper-Klasse erstellt man aus einer SwiftUI View einen UIKit Controller?

[1]:	https://blog.devgenius.io/combining-swiftui-and-uikit-a-guide-to-interoperability-4b458ee75b61

#learning unit#