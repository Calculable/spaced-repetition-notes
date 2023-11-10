# Swift Data - einfaches Schema
📐

```swift
import SwiftData

@Model
final class Trip {
    var name: String
    var bucketList: [BucketListItem]? = []
    var livingAccommodation: LivingAccommodation?

	//initializer
}
```

Mit `@Attribute` und `@Relationship` kann man es weiter konfigurieren

## ObservedObject

- Es wird automatisch zu Observable Object, @Published braucht es nicht mehr
- Wer das Model verwendet kann statt `@ObservedObject` neu `@Bindable` schreiben

## Zusammenfassung
- Welches Makro wird verwendet?
- Wie kann man es weiter konfigurieren?
- Wie verhält sich das Schema bezüglich Observing?

#learning unit# #Schema