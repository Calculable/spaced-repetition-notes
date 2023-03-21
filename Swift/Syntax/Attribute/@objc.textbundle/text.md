# @objc
🕸️

## Für was braucht man das @objc Attribut?

- Standartmässig generiert Swift nur Code, der nur innerhalb von Swift Code verwendet werden kann
- Wenn man jedoch mit der Objective-C Runtime interagiert (zum Beispiel, um UIKit zu verwenden), muss man den Code speziell kennzeichnen.

##  Beispiel
```swift
class MyController: UIViewController {
    @objc func authenticateUser() {

    }
}
```

Beispiel: Wenn man eine Methode von einem `UIBarButtonItem` oder von einem `Timer` aufrufen will, muss man es mit `@objc` annotieren. 

Der Compiler weisst einem darauf hin, wenn man die Annotation vergessen hat.

## Alle Methoden verfügbar machen

Wenn man gleich alle Methoden einer Klasse für die Objective-C Runtime verfügbar machen will, schreibt man:

```swift
@objcMembers class MyController: UIViewController {
    func login() {

    }
}
```


## Zusammenfassung
- Syntax
- Zweck

#learning unit#