# Detached Tasks
📎
## Weshalb braucht es Detached Tasks?

Zum Beispiel hier: Dieses Beispiel funktioniert nicht wie erwartet:

```swift
class ViewModel: ObservableObject { }

struct ContentView: View {
    @StateObject private var model = ViewModel()

    var body: some View {
        Button("Run", action: doWork)
    }

    func doWork() {
        Task {
            for i in 1...1000 {
                print("First \(i)")
            }
        }

        Task {
            for i in 1...1000 {
                print("Second \(i)")
            }
        }
    }
}
```

=\> Die beiden Tasks laufen nacheinander und nicht paralell

## Warum funktioniert das Beispiel nicht wie erwartet?

- Ein Task erbt die Priorität und den Actor-Context des Aufrufers
- Weil es in der ContentView ein @StateObject gibt, läuft der gesamte Code im MainActor!!
	- Bei State wäre es übrigens kein Problem


## Lösung: Detached Tasks

Man erstellt den Task mit `Task.detached { ... }`

- So wird die Priorität und der Actor-Context nicht vererbt.
- Man sollte das aber nur dann verwenden, wenn es nicht anderst geht

## Zusammenfassung
- Warum braucht man Detached Tasks? (Konkretes Beispiel)
- Anwendung

#learning unit#