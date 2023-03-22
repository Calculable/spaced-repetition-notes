# Initial View Controller festlegen

## Im Storyboard
![][image-1]

## Im Code

```swift
func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {
	
	guard let windowScene = (scene as? UIWindowScene) else {
		return
	}
	let window = UIWindow(windowScene: windowScene)
	window.rootViewController = createTabBarController()
	self.window = window
	window.makeKeyAndVisible()
	//...
}
```
## Zusammenfassung
- Nur Storyboard-Variante (nicht Code)

[image-1]:	assets/Bildschirmfoto%202021-09-01%20um%2012.10.53.png

#learning unit#