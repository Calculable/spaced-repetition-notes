# View neu zeichnen, wenn sich etwas im Array verändert
🧠

## Problem

- Eine SwiftUI hat Zugriff auf ein Array von Objekten
- Das UI soll aktualisiert werden, wenn sich ein Objekt innerhalb eines Arrays verändert

## Hinweise
- Arrays sind Structs
- Siehe auch Kapitel "State Missverständnis"

## Lösung 0: Mit Swift Data Funktioniert das Out-of-The-Box

## Lösung 1: Innerhalb des Arrays Struct-Elemente verwenden !

- Weil eine Änderung eines Structs immer die Änderung des ganzen Structs zur folge hat, wird das auch vom Array bemerkt!
- Bei Klassen hingegen funktioniert dieser Ansatz nicht

## Lösung 2: View aufsplitten

- Wenn das Array Klassen-Typen enthält, dann kann man die Darstellung so aufteilen, dass eine Sub-View jeweils nur ein Objekt darstellt. In der Sub-View kann man dann `@ObservedObject` verwenden

```swift
struct MyMainView {
	@State private var people: [Person] = []

	var body: some View {
		ForEach(people, id: \.self) { person in
			MySubView(person: person)
		}
		
	}
}
struct MySubView {
	@ObservedObject var person: Person

	var body: some View {
		Text("\(person.name)")
	}
}
```

## Lösung 3: Wrapper-Klasse um das Array bauen als ObservableObject

Bei Änderungen innerhalb des Arrays kann man dann den Wrapper über die Änderung informieren.

```swift
myWrapper.objectWillChange.send()
```

(Man kann das zum Beispiel in eine Wrapper-Klasse um das Array einbauen)


- Im Internet findet man auch solche generische Structs (ObservableArray<T>). Hier beobachtet das Array selbst seine enthaltenen Elemente und propagiert Änderungen an den Elementen.

## Zusammenfassung
- Mit SwiftData
- ohne SwiftData: Welche 3 Möglichkeiten gibt es, wenn man im UI über Änderungen an Objekten innerhalb eines Arrays informiert werden möchte?


#learning unit#