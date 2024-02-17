#  MacOS: File Referenzen
🪢

## Zweck
- Normale File-URLs haben das Proble dass der User nicht verschieben kann während die App läut
- Bei Referenz-URLs hingegen ist das möglich
- Eine Referenz sieht dan zum Beispiel so aus: `file:///.file/id=6571367.4836566`
- Die Referenz-URL ändert sich jedoch bei System-Neustarts (zum Persistieren eignen sich hingegen die [File Bookmarks][1])

## URL zu Referenz URL

Funktioniret bis jetzt nur mit NSURL:

```swift
if let fileRefURL = (url as NSURL).fileReferenceURL() as NSURL? { 
    print(fileRefURL)
	//Mit fileRefURL as URL? kann man es umwandeln
}
```

## Referenz URL zu URL

```swift
let url = URL(string: "file:///.file/id=6571367.4836566")
print(url!.absoluteString) //Gibt den Orginal-Pfad aus
```

## Zusamenfassung
- Wozu sind Bookmarks sinvoll (nur Konzept)
- Bleiben Bookmarks bei App-Neustart oder System-Neustart gültig?

[1]:	ulysses://x-callback-url/open?id=zr-47PCr9lYP_cfVv70QDw

#learning unit#