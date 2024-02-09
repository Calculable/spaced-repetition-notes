# Accessibility: Language
🦮

## SwiftUI

###  Standartsprache
Hier werden die Texte in der Sprache ausgegeben, in der die App läuft.
Es gibt KEINEN `accessibilityLanguage` Modifier


## UIKit

###  Standartsprache
Achtung: Die Standartsprache für die Voice-Over-Ausgabe ist per default die Sprache des Systems (nicht die Sprache der App!)

[https://www.reddit.com/r/iOSProgramming/comments/1aiiutz/confused\_about\_accessibilitylanguage/][1]

Man kann das jedoch fixen, indem man die `accessibilityLanguage` generell  für die gesamte App auf die App-Sprache setzt (im App Delegate):

```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    if let preferredLanguage = Bundle.main.preferredLocalizations.first {
        application.accessibilityLanguage = preferredLanguage
    }
    return true
}
```


### Beispiel

Für individuelle Views:

```swift
myLabel.accessibilityLanguage = "fr" //format: BCP 47
myLabel.accessibilityLabel = "Bonjour"
```

Man kann es auch wieder zurücksetzen:

```swift
myLabel.accessibilityLanguage = nil
```

## Zusammenfassung
- Standartwert für `acdessibilityLanguage` bei UIKit und SwiftUi

[1]:	https://www.reddit.com/r/iOSProgramming/comments/1aiiutz/confused_about_accessibilitylanguage/

#learning unit#