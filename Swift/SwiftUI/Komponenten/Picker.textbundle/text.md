# Picker
🧩

```swift
Picker("Select your student", selection: $selectedStudent){
	ForEach(students, id: \.self) { //ID ist wichtig
		Text($0)
    }
}            
```

Wenn man nicht `ForEach` verwendet, dann braucht jeder Eintrag einen `tag`
![][image-1]


**Wichtiger Hinweis**
Achtung - damit der Picker funktioniert, braucht es eine Navigation View. Ansonsten beim Klicken des Pickers keine View angezeigt werden

**Was ist, wenn man keine ID angibt?**

- Beim Selected Item wird statt der ID der Index gespeichert:
- Wenn man also hier 2 Personen auswählt, dann steht danach bei `numberOfPeople` der Wert `0` drin.

```swift
Picker("Number of people", selection: $numberOfPeople) {
        ForEach(2 ..< 100) {
            Text("\($0) people")
        }
    }
```

## Learning: SwiftUI - Picker mit Optional Selection funktioniert nicht
🧠

Das Funktioniert nicht:

```swift
struct ExampleView: View {

    @State var selectedExample: ExampleModel? = nil

    var body: some View {

        Picker("", selection: $selectedExample){
            //...
        }
    }
}
```

- Problem: Selection soll nicht ein optional sein
- Lösung: Default-Wert

```swift
@State var selectedExample: ExampleModel? = .example
```

## Zusammenfassung
Wie macht man einen Picker?

[image-1]:	assets/Bildschirmfoto%202022-07-20%20um%2018.08.24.png

#learning unit#