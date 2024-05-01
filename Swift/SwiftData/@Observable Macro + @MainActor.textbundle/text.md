# @Observable Macro + @MainActor

## Problem: @Observable Macro + @MainActor sind schlecht kombinierbar

### Früher
Früher hat man in der Regel so etwas verwendet:

```swift
@MainActor
class ObservableObject1: ObservableObject {
    @Published var title = "Hello"
}
```


### iOS 17
Heute schreibt man:

```swift
@Observable class ObservableObject2 {
    var title = "Hello"
}
```

Wenn man aber ``@Observable``` und `@MainActor` kombiniert, dann bekommt man diesen Fehler beim Aufrufen des Constructors aus einer View:

> Call to main actor-isolated initializer 'init()' in a synchronous nonisolated context
=\> Man müsste also auch die View als @MainActor kennzeichnen, was aber nicht best-practice ist

##  Lösung

###  Lösung 1: Properties mit @MainActor kennzeichnen

```swift
@Published var title = "Hello"
```
=\> Jetzt bekommt man einen Compiler Fehler wenn man das Attribut aus einem nicht-isolierten Kontext aufruft.

Nun muss man selber sicherstellen, dass man das Attribut nur aus dem MainActor ändert:

```swift
@MainActor
func updateTitle() {
	title = "xy"
}
```

###  Lösung 2

- Sowohl ViewModel als auch View als ganzes mit `@MainActor` annotieren

> In the old world, having a @StateObject used to infer a @MainActor for the whole View. The @State doesn't make the same inference. (...) I think we should continue to explicitly mark VMs as @MainActor, and manually mark the view as @MainActor, since this was already happening under the hood.


## Vorsicht - keine Warnungen mehr!

###  Früher

(Wenn man den `title` angepasst hat aus einem nicht-main-thread, hat man eine Runtime-Warnung bekommen):

```swift
Task {
	observableObject.title = xy
}
```

![][image-1]

### iOS 17
- Heute bekommt man diese Warnung nicht mehr!

## Quelle
[https://www.youtube.com/watch?v=4dQOnNYjO58][1]


##  Zusammenfassung
- Wie sollte man @MainActor gemeinsam mit @Observable gebrauchen?

[1]:	https://www.youtube.com/watch?v=4dQOnNYjO58

[image-1]:	assets/Bildschirmfoto%202024-04-08%20um%2021.34.56.png

#learning unit#