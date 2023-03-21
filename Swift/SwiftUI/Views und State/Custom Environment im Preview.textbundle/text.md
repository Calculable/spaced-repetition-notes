# Custom Environment im Preview
🌳


```swift
struct MyView_Preview: PreviewProvider {
    static var previews: some View {   
        let myCustomObject = /*...*/
     
        MyView(content)
			.environmentObject(myCustomObject)
            .environment(\.managedObjectContext, myCustomManagedObjectContext)    
}
```

## Zusammenfassung
- Wie kann man dem Preview eigene Environment-Variabeln / Environment-Objekte mitgeben?

#learning unit#