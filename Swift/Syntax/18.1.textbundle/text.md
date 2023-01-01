# Primary Associated Types 🥇
::18.1::
Folgender Code ist nicht erlaubt:

```swift
class  MusicPlayer { 
	func  play(_  playlist: Collection) { /* ... */ }
}
```

Dies liegt daran, dass Collection ein Protokoll mit Associated Types ist. Diese müssen zuerst ausgefüllt werden (oder man verwendet TypeErasure). Neu mit Swift 5.7 darf man auch folgendes Schreiben:

```swift
class  MusicPlayer { 
	func  play(_  playlist: some  Collection) { /* ... */ }
}
```

Aber auch diese Lösung hat ein Problem. Wir wollen zum Beispiel, dass innerhalb der Collection nur "Tracks" sein dürfen.

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