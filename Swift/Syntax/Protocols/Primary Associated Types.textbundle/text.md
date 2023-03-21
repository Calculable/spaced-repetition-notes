# Primary Associated Types
🥇


Dieser Code hat ein Problem: Wir wollen zum Beispiel, dass innerhalb der Collection nur "Tracks" sein dürfen:

```swift
class MusicPlayer { 
	func  play(_  playlist: some  Collection) { /* ... */ }
}
```

Deshalb kann man jetzt Primary Associated Types angeben (das sieht aus wie ein Generic). Hier ein Beispiel aus dem bereits existierenden Colleciton-Protokoll:

```swift
public protocol Collection<Element>: Sequence {
	associatedtype Element 
	associatedtype Iterator  =  IndexingIterator<Self>
	associatedtype SubSequence : Collection  =  ///...
}
```

Jetzt kann man es so verwenden:

```swift
class  MusicPlayer { 
	func  play(_  playlist: some  Collection<Track>) { /* ... */ }
}
```

Alternativ könnte man auch folgendes schreiben:

```swift
class  MusicPlayer {
	func  play<Playlist: Collection<Track>>(_  playlist: Playlist) { /* ... */ }
}
```

## Zusammenfassung
Wozu ist das gut?
Codebeispiel

#learning unit#