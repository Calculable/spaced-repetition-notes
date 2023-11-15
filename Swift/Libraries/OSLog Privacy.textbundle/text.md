# OSLog Privacy
🌫️

## Beispiel
```swift
Logger.viewCycle.info("User \(username, privacy: .private) logged in")
```

- So werden die Logs in externen Tools wie der Console app nicht mehr angezeigt, aber wir sehen es beim Debuggen

## Welche Optionen gibt es?

```swift
static var auto: OSLogPrivacy //The standard option to let the system determine whether to redact or display a value. (Standartmässig aktiviert)

static var `private`: OSLogPrivacy //The standard option to always redact the interpolated value.

static var `public`: OSLogPrivacy //The standard option to always show the interpolated value.

static var sensitive: OSLogPrivacy //The option to always redact interpolated values that contain sensitive information.

```

Der Unterschied zwischen `private` und `sensitive` ist rein semantisch für die Entwickler als Dokumentation.

## Zusammenfassung
- Wie kann man mit einem OSLogger die privaten Userdaten schützen (Codebeispiel)


#learning unit#