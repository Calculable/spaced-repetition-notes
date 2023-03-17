# Store Object Pattern
💾

## Was sind Store Objects?

> Store objects responsible for storing the state and providing actions to mutate that state. You can have as many store objects as you need to keep them simple and responsible for a small part of your app state. For example, you may have `SettingsStore` to keep a state of user-defined settings and `TodoStore` to keep user tasks.

```swift
final class TodosStore: ObservableObject {
    @Published var todos: [Todo] = []

    func orderByDate() {
        todos.sort { $0.date < $1.date }
    }

    func orderByPriority() {
        todos.sort { $0.priority > $1.priority }
    }

    func removeCompleted() {
        todos.removeAll { $0.isDone }
    }
}

```

Der Store wird oft als EnvironmentObject an die Views gegeben:

```swift
@EnvironmentObject var store: TodosStore
```

## Store Objects
- Was sind Store Objects
- Wie werden Store Objects an die View gegeben?


#nur learning unit# #learning unit#