# AppDelegate, SceneDelegate
🔄


## App Delegate
- Hier werden Dinge konfiguriert, welche die ganze App betreffen (Zum Beispiel Push-Notification)

	- Starten der app
	- Beenden der App
	- Übergänge in den Vordergrund oder Hintergrund
	- Empfangen von Notifications etc.
	- Auf URL Scheme Links reagieren...

## Scene Delegate
- Hier wird geregelt, was auf dem Screen angezeigt wird
- Auf dem iPad können mehrere Instanzen der gleichen App (mehrere Scenes) angezeigt werden
- In der Scene Delegate Klasse kann man auf den App Lifecycle zugreifen. Siehe auch Kapitel Scene Delegate Lifecycle Methoden

### Scene Delegate Lifecycle Methoden

- `sceneDidBecomeActive`
- `sceneWillResignActive`: Zum Beispiel bei einem eingehenden Telefonanruf
- `sceneWillEnterForeground`
- `sceneDidEnterBackground`: Um Daten zu speichern, Ressourcen Freizugeben etc.


## Siehe auch

Siehe auch "UIApplicationDelegate in SwiftUI" [ulysses://x-callback-url/open?id=P3MAxAn7zwu0CGrW562hJQ][1]

## Zusammenfassung
- Wozu ist das App Delegate?
- Wozu ist das Scene Delegate?


[1]:	ulysses://x-callback-url/open?id=P3MAxAn7zwu0CGrW562hJQ

#learning unit# #guide