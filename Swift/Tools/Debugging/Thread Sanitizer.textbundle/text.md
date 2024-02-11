# Thread Sanitizer
🩹
- Auch als **TSan** bezeichnet
- Damit kann man Data Races erkennen: Wenn auf den gleichen Memory-Abschnitt von mehreren Threads aus zugegriffen wird ohne Synchronisation (und nicht ausschliesslich lelsend)
- Wird in den Runtime Settings aktiviert:

![][image-1]
- Achtung: Damit man es aktivieren kann darf als Runtime nicht ein Simulator ausgewählt sein
- Man kann es auch für das Test-Schema aktivieren
- Achtung: Durch das aktivieren der Option wird die App 2x bis 20x Langsamer
- Es werden zum Beispiel folgende Dinge erkannt:

```swift
private var example: String = ""

func updateName() {
	Task {
		self.example.append("Test)
	}

	//Main Thread
	print(self.example) ⚠️ //Hier kommt eine Warnung dass gleichzeitig gelesen und geschrieben wird
}
```


##  Zusammenfassung
- Was macht der Thread Sanitizer?

[image-1]:	assets/Bildschirmfoto%202024-02-10%20um%2008.44.27.png

#learning unit#