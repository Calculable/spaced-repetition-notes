# Tree
🌳

## Begriffe
- **Root**-Objekt
- **Branch**-Objekt
- **Leaf**-Objekt

## Implementation (gekürzt)

```swift
struct Node<Value> {
    var value: Value
	private(set) var children: [Node]

	init(_ value: Value) {
	    self.value = value
	    children = []
	}

	mutating func add(child: Node) {
	    children.append(child)
	}

}
```

- Manchmal wird noch ein Wrapper für den Root gemacht, das ist aber nicht zwingend nötig.

- Hinweis: Oft möchte man hier stattdessen Class verwenden, damit man jeweils nicht Kopien der einzelnen Elemente modifiziert.

- Siehe Hacking With Swift für die vollständige Implementation

## Zusammenfassung
- 3 verschiedene Namen für die Nodes
\- 
\- 


#nur learning unit# #learning unit#