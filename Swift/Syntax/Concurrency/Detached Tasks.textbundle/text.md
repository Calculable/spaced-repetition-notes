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

=\> Die beiden Tasks laufen nacheinander und nicht paralell. Zudem wird dadurch das UI blockiert

## Warum funktioniert das Beispiel nicht wie erwartet?

- Ein Task erbt die Priorität und den Actor-Context des Aufrufers
- Weil es in der ContentView ein @StateObject gibt, läuft der gesamte Code im MainActor!!
	- Bei State wäre es übrigens kein Problem


## Lösung: Detached Tasks

Man erstellt den Task mit `Task.detached { ... }`

- So wird die Priorität und der Actor-Context nicht vererbt.
- Man sollte das aber nur dann verwenden, wenn es nicht anderst geht

## Man kann auch eine Priorität angeben:

```swift
Task.detached(priority: .background) {
    // Runs asynchronously
}
```

##  Hinweis
- Wenn der Parent-Task gecanceled wird, werden detached child-tasks nicht gecanceled.

> Detached tasks should be your last resort. In many cases, you’ll be able to run tasks in parallel using task groups instead and benefit from parent-child relationships. 
## Zusammenfassung
- Warum braucht man Detached Tasks? (Konkretes Beispiel)
- Anwendung

#learning unit#