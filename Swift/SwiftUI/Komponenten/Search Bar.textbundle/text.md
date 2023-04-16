# Search Bar
🧩

```swift

struct ContentView: View {
    @State private var searchText = ""
    let allNames = ["Subh", "Vina", "Melvin", "Stefanie"]

    var body: some View {
        NavigationView {
            List(filteredNames, id: \.self) { name in
                Text(name)
            }
            .searchable(text: $searchText, prompt: "Look for something")
            .navigationTitle("Searching")
        }
    }

    var filteredNames: [String] {
        if searchText.isEmpty {
            return allNames
        } else {
            return allNames.filter { $0.localizedCaseInsensitiveContains(searchText) }
        }
    }
}
```

![][image-1]

Jetzt kann man es runterziehen:

![][image-2]

Man kann das Suchfeld aber auch an gewöhnliche Elemente hängen, nicht nur Listen:

```swift
NavigationView {
	Text("Searching for \(searchText)")
		.searchable(text: $searchText, prompt: "Look for something")
		.navigationTitle("Searching")
}
```
![][image-3]

##  Mit Search Suggestions

```swift
.searchable(text: $model.searchString) {
	ForEach (model.searchSuggestions) { suggestion in
		Text(suggestion.name).searchCompletion (suggestion.name)
		}
	}
```


![][image-4]


## Zusammenfassung
- Wie macht man eine Liste durchsuchbar mit einer Search-Bar?

[image-1]:	assets/Bildschirmfoto%202022-08-24%20um%2008.30.35.png
[image-2]:	assets/Bildschirmfoto%202022-08-24%20um%2008.30.54.png
[image-3]:	assets/Bildschirmfoto%202022-08-24%20um%2008.33.35.png
[image-4]:	assets/Bildschirm%C2%ADfoto%202023-04-16%20um%2012.41.35.png

#learning unit#