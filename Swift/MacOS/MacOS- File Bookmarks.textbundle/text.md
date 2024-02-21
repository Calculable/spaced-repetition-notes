#  MacOS: File Bookmarks
🔖

## Zwecke
- Wenn der User einmal die Berechtigung für ein File gegeben hat und man nach einem Neustart der App nicht erneut danach fragen möchte
- Wenn der User Dateien verschiebt, können sie weiterhin gefunden werden, auch wenn die App in der Zwischenzeit geschlossen und erneut geöffnet wurden (Hinweis: File-Referenzen hingegen ändern sich bei einem System-Neustart)

## Vorgehen
- User wählt eine Datei
- Während die App läuft kann man mit File-Referenzen arbeiten (So kann der User die Dateien auch verschieben): [Siehe File Referenzen][1]
- Beim Schliessen der App speichert man sich alle Bookmarks

## URL zu Bookmark

```swift
let bookMarkData = try url.bookmarkData(options: .withSecurityScope, includingResourceValuesForKeys: nil, relativeTo: nil)
```

Wenn man die Datei in Zukunft nicht menr schreiben muss kann man als Scope `securityScopeAllowOnlyReadAccess` angeben

## Bookmark persistiern
- Man kan einfach das `Data`-Objekt in NSUserDefaults oder ein File schreiben

## Bookmark zu URL
```swift
do {
    var isStale = false;
    let bookMarkUrl = try URL(resolvingBookmarkData: bookMarkData, options: .withSecurityScope, relativeTo: nil, bookmarkDataIsStale: &isStale);

    if(!isStale) {
        if(bookMarkUrl.startAccessingSecurityScopedResource()) {
            //Do something with the file ✅
            bookMarkUrl.stopAccessingSecurityScopedResource()
        } else {
            // Cannot access security scoped resource.
        }
    } else {
        // The bookmark is stale
    }
} catch {
    // Error creating a URL from the bookmark
}
```

Oder etwas einfacher:

```swift
do {
  let location = try URL(resolvingBookmarkData: bookmark)
  defer {
    location.stopAccessingSecurityScopedResource()
  }
  // Use the resource at the location URL.
}
catch let error {
  // Handle any errors.
} 
```


## Zusammenfassung
- Wozu sind Bookmarks sinvoll
- Bleiben Bookmarks bei App-Neustart oder System-Neustart gültig?

[1]:	ulysses://x-callback-url/open?id=iTQbUaccEyEAcTAFWjVfVw

#learning unit#