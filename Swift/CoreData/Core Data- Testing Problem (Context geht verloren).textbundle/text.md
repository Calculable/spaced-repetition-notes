# Core Data: Testing Problem (Context geht verloren)
📟

## Der folgende Test schlägt fehl:

```swift
func createExampleItem() -> Item {
	let result = DataController(inMemory: true) //lokale Instanz
	let viewContext = result.container.viewContext
	let item = Item(context: viewContext)
	return item
}
```

```swift
func testExampleProjectIsClosed() {
    let project = createExampleItem()
    XCTAssertTrue(project.closed)
}
```

## Warum ist das so?

Die Properties von `Item` werden ja von Core Data verwaltet:

```swift
@NSManaged public var closed: Bool
```

Im Code oben verwendet man jedoch eine lokale Instanz von `DataController` mit lokalem Scope. Diese geht verloren, wenn der das Item zurückgegeben wird. 

Das heisst, dass `Item` kann auch nicht mehr gemanaged werden (Verhalten ist undefiniert)

## Lösung

Man kann einfach die Singleton-Instanz verwenden, diese geht nicht verloren:

```swift
let controller = DataController.preview
```

Vorsicht: Man sollte beachten, dass diese Instanz zwischen allen Tests geteilt wird, weil es sich um ein Singleton handelt.

## Zusammenfassung

- Welches Problem tritt auf, wenn man einen lokalen `DataController`, bzw. `viewContext` verwendet?


#nur learning unit# #learning unit#