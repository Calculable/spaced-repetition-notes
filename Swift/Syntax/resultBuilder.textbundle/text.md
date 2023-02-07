# resultBuilder
👷‍♂️

## Verwendung

- FunctionBuilder gibt es seit Swift 5.1
- Man kann damit Code wie diesen bauen:

```swift
let terry = Node("Terry") {
    Node("Paul") {
        Node("Sophie")
        Node("Lottie")
    }

    Node("Andrew") {
        Node("John")
    }
}
```

Beachte: Es handelt sich um ein Trailing Closure, aber darin muss man nicht ein Array verwenden, sondern kann einfach mehrere `Nodes` aufzählen.


## Implementation (nicht auswendig)

Man braucht ein separates Struct, welches mit `@functionBuilder` annotiert ist:

```swift
@resultBuilder
struct NodeBuilder {
    static func buildBlock<Value>(_ children: Node<Value>...) -> [Node<Value>] {
        children
    }
}
```

Im Struct `Node` kann man den NodeBuilder dann so verwenden:

```swift
struct Node {
	
	//...

	init(_ value: Value, @NodeBuilder builder: () -> [Node]) {
	    self.value = value
	    self.children = builder()
	}

}
```

## Diskussion

> Although function builders aren’t to everyone’s tastes, it’s great to have it as an option here – use them if you prefer them, or take the manual approach instead.

## Zusammenfassung
- Wie funktioniert der Function Builder konzeptionell?
- Wie wird es am Schluss angewendet?


#nur learning unit#