# Unit Testing: Teardown Block 👁️‍🗨️
::53.1::

Manchmal braucht man einen Teardown, man möchte aber die Flexibilität haben, dass es nur nach gewissen Tests ausgeführt wird und nicht nach jedem Test:

```swift
func connectToDatabase() -> Database {
    let database = Database()
    database.connect()

    addTeardownBlock {
        database.cleanUp()
    }

    return database
}
```


## Zusammenfassung
- Was ist ein Teardown Block?
- Wie wird er angewendet?