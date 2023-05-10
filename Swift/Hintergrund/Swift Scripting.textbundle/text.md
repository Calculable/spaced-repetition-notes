# Swift Scripting
🖊️
## Compiled vs. Interpreted

- Swift ist eine kompilierte Sprache
- Skripts benötigten jedoch eine Interpretierte Sprache
- Deshalb gibt es Swift REPL, um Swift Code zu interpretieren. 

## Einfaches Skript (ohne Package)

```swift
#!/usr/bin/swift
print("Hello, world!")
```

Es benötigt noch:

```swift
chmod +x myFile.script
```

anschliessend kann man es starten:

```swift
./myFile.script
```

alternativ:

```swift
swift main.swift
Hello, world!
```

##  Einfaches Skript mit Package

Vorteil: Man kann das Projekt mit Xcode bearbeiten und hat Fehler und Warnungen (das hätte man mit einem einzelnen File nicht)


```swift
> mkdir ScriptingWithSwift
> cd ScriptingWithSwift
> touch Package.swift
> touch main.swift
```

Innerhalb von `Package.swift`:

```swift
// swift-tools-version:5.7
import PackageDescription

let name = "HelloWorld"
let package = Package(
  name: name,
  platforms: [.macOS(.v12)],
  targets: [
    .executableTarget(name: name, path: "")
  ]
)
```


=\> Ansonsten gleich wie Kapitel „Einfaches Skript“

##  Zusammenfassung
- Wie schreibt man ein einfaches Skript (ohne Package)

#learning unit#