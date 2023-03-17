# Pattern: Enums statt Optionals
🪸
## Problem

Häufig hat man Views mit Optionalen Properties und muss diese jeweils unterscheiden:

```swift
struct ProductView: View {
    var selectedProduct: Product?

    var body: some View {
        //show product if not nil, otherwise show default-view
    }
}
```

## Lösung

Wenn man ein Enum verwendet statt dem optionalen Property, dann kann man seine Absichten besser ausdrücken:

```swift
enum ViewingMode {
    case selectedProduct(product: Product)
    case empty
}

struct ProductView: View {
    var mode: ViewingMode

    var body: some View {
        switch mode {
			case .selectedProduct(let product): 
				//...
			case .empty:
				//...
		}
    }
}
```

## Zusammenfassung
- Wie funktioniert das Pattern?


#nur learning unit# #learning unit#