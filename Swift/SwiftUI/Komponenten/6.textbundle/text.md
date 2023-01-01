# Alert 🧩
::6::

##  mit Boolean

```swift
struct ContentView: View {
    @State private var showingAlert = false

    var body: some View {
		Button("Show Alert") {
		    showingAlert = true
		}
		.alert("Important message", isPresented: $showingAlert) {
		    Button("OK", role: .cancel) { }
		} message: {
		    Text("Please read this.")
		}
    }
}
```


## mit Optional

```swift
.alert("Welcome", isPresented: $isShowingUser, presenting: selectedUser) { user in
    Button(user.id) { }
}
```

## Zusammenfassung
- Wie macht man einen Alert mit Bool?
- Wie macht man einen Alert mit Optional?
- Wie ist ein Alert mit Buttons und Inhalt aufgebaut?