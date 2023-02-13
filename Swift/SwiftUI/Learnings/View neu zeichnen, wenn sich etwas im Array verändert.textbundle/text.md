# View neu zeichnen, wenn sich etwas im Array verändert
🧠

## Problem

- Eine SwiftUI hat Zugriff auf ein Array von Objekten
- Das UI soll aktualisiert werden, wenn sich ein Objekt innerhalb eines Arrays verändert

## Hinweise
- Arrays sind Structs
- Siehe auch Kapitel "State Missverständnis"

## Lösung 1: Innerhalb des Arrays Struct-Elemente verwenden

- Weil eine Änderung eines Structs immer die Änderung des ganzen Structs zur folge hat, wird das auch vom Array bemerkt
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

## Lösung 3: Das Array manuell über die Änderung informieren

```swift
people.objectWillChange.send()
people[0].name = "changed"
```

(Man kann das zum Beispiel in eine Wrapper-Klasse um das Array einbauen)


## Lösung 4: ObservableArray<T>

- Im Internet findet man solche generische Structs. Hier beobachtet das Array selbst seine enthaltenen Elemente und propagiert Änderungen an den Elementen.

## Zusammenfassung
- Welche 4 Möglichkeiten gibt es, wenn man im UI über Änderungen an Objekten innerhalb eines Arrays informiert werden möchte?


#nur learning unit#