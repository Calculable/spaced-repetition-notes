# Combine: Future und Promises
🔀

Nicht genau angeschaut, weil es neu ja die Async/Await Syntax gibt

- a `Future` delivers exactly one value (or an error) and completes
- ... it's a lightweight version of publishers, useful in contexts where you'd use a closure callback

> While async/await might be the preferred way to handle asynchronous tasks in Swift due to its simplicity and readability, Futures and Promises can still be used where they make sense, and they might be more suitable for certain use cases.


Beispiel Anwendungsfall für ein Future:

```swift
@Published var username: String = ""

var validateUsername: AnyPublisher<String?, Never> {
	return $username
		.debounce(for: 0.5, scheduler: RunLoop.main)
		.removeDuplicates()
		.flatMap {
			username in
				return Future { promise in
					self.usernameAvailable(username) { available in
						promise(.success(available ? username : nil))
					}
				}
		}
		.eraseToAnyPublisher()
}
```

##  Zusammenfassung
- Nur Konzept: Was ist ein Future?

#learning unit#