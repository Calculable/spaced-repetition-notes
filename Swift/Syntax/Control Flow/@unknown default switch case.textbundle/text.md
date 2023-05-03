# @unknown default switch case
🤔
Man verwendet das, wenn man alle Enum-Cases abgedeckt hat. Normalerweise braucht man dann kein `default`. Hier möchte man aber vom Compiler gewarnt werden, wenn ein neues Switch-Statement dazu kommt.

```swift
switch status {
case .first:
    //do something
case .second:
    //do something
@unknown default:
    //do something
}
```


Der Vorteil davon: Wenn neue Enums dazu kommen, dann gibt es keine Fehlermeldung im Code.


## Zusammenfassung
- Zweck / Syntax

#learning unit#