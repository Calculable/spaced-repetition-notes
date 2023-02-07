# Custom UserDefaults im Preview ⚙️


```swift
struct MyView_Preview: PreviewProvider {
    static var previews: some View {   

        let customUserDefaults: UserDefaults = {
            let newUserDefaults = 
				UserDefaults(suiteName: "preview_user_defaults")!
            
			newUserDefaults.set(true, forKey: "mySetting")
            return newUserDefaults
        }()  
     
        MyView(content)
			.defaultAppStorage(customUserDefaults)
}
```

## Zusammenfassung
- Wie kann man für das Preview eigene UserDefaults festlegen?