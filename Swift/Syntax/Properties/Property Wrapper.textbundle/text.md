# Property Wrapper
📦

## Wie funktionieren Property Wrapper?
- Hinter jedem Property Wrapper ist ein Struct
- Zum Beispiel steht hinter `@State` und `@Environment` immer ein Struct. (`State<Value>`)


##  Custom Property Wrapper (nicht auswändig)

### Custom Property Wrapper Definition
```swift
@propertyWrapper
struct NonNegative<Value: BinaryInteger> {
    var value: Value

    init(wrappedValue: Value) {
        if wrappedValue < 0 {
            value = 0
        } else {
            value = wrappedValue
        }
    }

    var wrappedValue: Value {
        get { value }
        set {
            if newValue < 0 {
                value = 0
            } else {
                value = newValue
            }
        }
    }
}
```

### Custom Property Wrapper Verwendung
```swift
struct User {
    @NonNegative var score = 0
}
```

## Beispiel: Generic Property Wrapper

```swift
@propertyWrapper struct NonNegative<Value: SignedNumeric & Comparable> {
    var value: Value

    init(wrappedValue: Value) {
        self.value = max(0, wrappedValue)
    }

    var wrappedValue: Value {
        get { value }
        set { value = max(0, wrappedValue) }
    }
}
```


Property Wrapper with Dynamic Property

### Um was geht es in diesem Beispiel?

- Man möchte einen Property-Wrapper bauen, der den Zugriff auf ein File vereinfacht
- Wenn sich der Text ändert, soll die Änderung direkt in das File geschrieben werden.
- Beim Initialen Laden soll der Inhalt aus dem Text-File geladen werden.

### Property Wrapper


```swift
@propertyWrapper struct Document: DynamicProperty { //Mit der Annotation DynamicProperty wird SwiftUI darüber informiert, wenn sich etwas verändert und es kann erneut den Getter aufrufen
    @State private var value = ""
    private let url: URL

	init(_ filename: String) {
	    let paths = FileManager.default.urls(for: .documentDirectory, in: .userDomainMask)
	    url = paths[0].appendingPathComponent(filename)

	    let initialText = (try? String(contentsOf: url)) ?? ""
	    _value = State(wrappedValue: initialText)
	}
    
	var wrappedValue: String {
	    get {
	        value
	    }
	    nonmutating set { //beachte: weil value ein State ist, also von SwiftUI verwaltet wird, kann man hier einen nonmutating setter verwenden, weil sich am eigentlichen Document nichts ändert
	        do {
	            try newValue.write(to: url, atomically: true, encoding: .utf8)
	            value = newValue
	        } catch {
	            print("Failed to write output")
	        }
	    }
	}
	
	var projectedValue: Binding<String> { //mit `"projected" value kann man alternative Arten anbieten, um den Property Wrapper zu verwenden. In unserem Beispiel ist das ein Binding. Beachte: Im Anwendungs-Code wird einfach direkt das Binding verwendet, ohne dass "projected" Value irgendwo erwähnt ist
	    Binding(
	        get: { wrappedValue },
	        set: { wrappedValue = $0 }
	    )
	}
}
```





### Property Wrapper anwenden


```swift
struct ContentView: View {
    @Document("test.txt") var document
    
    var body: some View {
	    Text(document) //use getter (automatically updated)
		TextEditor(text: $document) //use projected value
		Button("Change document") { //use non-mutating setter
		    document = String(Int.random(in: 1...1000))
	    }
    }
}
```



## Zusammenfassung
Zweck
Custom Property Wrapper (nur Konzept)

#learning unit#