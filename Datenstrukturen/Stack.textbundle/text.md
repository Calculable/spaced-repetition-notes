# Stack
🥞

## Verhalten
- LIFO: "Last in, First Out"
- Zwei Operationen: Push und Pop, Peek (Optional)
			 
## Implementation (gekürzt)

```swift
struct Stack<Element> {
	private var array = [Element]()

	mutating func push(_ element: Element) {
	    array.append(element)
	}
	
	mutating func pop() -> Element? {
	    array.popLast()
	}

}
```

Siehe Hacking With Swift für die vollständige Implementation 

## Zusammenfassung
- 2 (bzw. 3) Operationen (Konzept)
			 


#nur learning unit# #learning unit#