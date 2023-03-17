# NS Cache
💾

##  Zweck
Funktioniert wie ein Dictionary, aber: iOS entfernt automatisch Inhalte, wenn das Gerät nicht mehr viel Speicherplatz hat.

##  Beispiel
So arbeitet man mit dem Cache:

```swift
let cache = NSCache<NSString, ExpensiveObjectClass>()
let myObject: ExpensiveObjectClass
```

## Zugriff / Speichern
```swift
if let cachedVersion = cache.object(forKey: "CachedObject") {
    // use the cached version
    myObject = cachedVersion
} else {
    // create it from scratch then store in the cache
    myObject = ExpensiveObjectClass()
    cache.setObject(myObject, forKey: "CachedObject")
}
```

## Zusammenfassung
- Wie wird der NSCache angewendet?

#learning unit#