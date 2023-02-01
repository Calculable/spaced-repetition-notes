# DynamicMemberLookup 🔎


## Code
```swift
@dynamicMemberLookup
struct JSON {
	subscript(dynamicMember key: String) -> XY {
	    //do something with the key
	}
}
```

## Verwendung

Jetzt kann man beliebige "Members verwenden:

```swift
JSON().hello
```

## Zusammenfassung
- Was ist DynamicMemberLookup?


#nur learning unit#