# Argument Parser
📃

## Einstiegspunkt

```swift
@main
struct App: ParsableCommand {
    func run() {
        print("Hello from Swift Argument Parser!")
    }
}
```

## Flag

Innerhalb des App-Structs:

```swift
@Flag(name: .shortAndLong, help: "Neatly formats the output.")
var prettify = false
```

Wenn `shortAndLong` aktiviert ist, kann der Nutzer sowohl `-p` als auch `-prettify` eingeben.



## Argument

Innerhalb des App-Structs:

```swift
@Argument(help: "The filename you want to process.")
var file: String
```

## Wie hat man Zugriff auf die Werte?

- Sie wurden automatisch in die Variabeln gefüllt.

## Command Configuration

Damit kann man einige globale Einstellungen für die Applikation festlegen:

```swift
tatic var configuration: CommandConfiguration {
    CommandConfiguration(commandName: "jsontidy", abstract: "Adjusts JSON files to compress or expand data, and also provide key sorting.")
}
```

## Zusammenfassung

- Zu was muss `App` konform sein?
- Welche zwei Arten von Informationen können entgegengenommen werden? (Property Wrapper ohne Details)



#nur learning unit#