# Optional Observable
🧠

##  Problem

Folgendes ist nicht möglich:

```swift
struct LearningNavigationView: View {
	@ObservableObject var parentCollection: LearningUnitCollection?
}
```
## Lösung

Man teilt die View einfach so auf, dass die Sub-Views mit einer nicht-Optionalen Variante arbeiten:


```swift
struct MainView: View {
	var myObject: MyObservableObject?

	var body: some View {
		if let myObject {
			SubView(myObject)
		}
	}


}

```
 
```swift
struct SubView: View {
    @ObservedObject var myObject: MyObservableObject
    
    var body: some View {
		//...
    }
}
```

## Zusammenfassung?
- Was macht man, wenn man ein optionales ObservableObject beobachten möchte?
