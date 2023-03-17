# Learning: State Management
🧠

##  Frage: Wie verhält sich der folgende Code?

```swift
class StringBox: ObservableObject, Identifiable {
    @Published var value: String
    
    init() {
        value = UUID().uuidString
    }
    
    func change() {
        value = UUID().uuidString
    }
}

struct ArrayDisplayView: View {
    var myArray: [StringBox]
    var myStructArray: [String]

    var body: some View {
        VStack {
            List {
                Section("Boxes") {
                    ForEach(myArray) {
                        Text($0.value)
                    }
                }
               
                Section("Structs") {
                    ForEach(myStructArray, id:\.self) {
                        Text($0)
                    }
                }
            }
        }
    }
}

struct ContentView: View {
    
    @State var myBoxArray: [StringBox] = [StringBox()]
    @State var myStructArray: [String] = [UUID().uuidString]

    var body: some View {
        
        VStack {
            Button("Append to box array") {
                myBoxArray.append(StringBox())
            }
            
            Button("change first in box array") {
                myBoxArray[0].change()
            }
            
            Button("Append to struct array") {
                myStructArray.append(UUID().uuidString)
            }
            
            Button("change first in struct array") {
                myStructArray[0] = UUID().uuidString
            }
            
            Divider()
            ArrayDisplayView(myArray: myBoxArray, myStructArray: myStructArray)
        }
    }
}
```

![][image-1]

## Antwort

- Die View wird bei jedem Button neu gezeichnet, ausser bei `change first in box array`

- Dies liegt daran, dass ein Array nur eine Veränderung bemerkt, wenn neue Items hinzugefügt werden oder wenn ein Objekt vollständig ersetzt wird. 
	- Bei Structs ist das immer der Fall wenn sie verändert werden, weil eine Änderung am Struct immer ein neues Struct erzeugt
- Beim Box-Type bekommt das Array die Änderung also nicht mitüber. =\> Auch dann nicht wenn man explizit `box.objectWillChange.send()` aufruft
- Denn das Array beobachtet nicht seine Kinder!
- Es würde auch nichts ändern, wenn man in der View `@Binding var myArray: [StringBox]` verwenden würde.

## Mögliche Lösungen

Siehe Kapitel: „View neu zeichnen, wenn sich etwas im Array verändert“

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-04%20um%2010.56.48.png

#nur learning unit# #learning unit#