# Actors
🕴️

##  Zweck

- Wenn man auf ein Objekt nur aus einem Thread zur gleichen Zeit zugreifen darf
- Verhindert Data Races
- Beispiel: Database Access - um zu verhindern dass widersprüchliche Informationen gespeichert werden


##  Beispiel Code

```swift
actor User {
    var name = 10

    func printName() {
        print("I am \(score)")
    }

    func copyName(from other: User) async {
        name = await other.name
    }
} 
```

## Verhalten
- Fast gleich wie eine Klasse
	- Reference Type
	- Es kann Properties, Methoden, Initializer, Subscripts, Generics Protokollkonformität etc. geben
- Vererbung wird nicht unterstützt
- Es ist automatisch konform zum „Actor“ protocol

##  Auswirkung: Actor Isolation

- Wenn man von aussen auf Properties und Methoden zugreift muss mann immer `await` verwenden
	- Ausnahme: Konstanten oder `nonisolated` (siehe separates Kapitel)
- Das macht Sinn, weil man ja allenfalls warten muss, bis das Objekt verfügbar ist
- Beachte im Codebeispiel: Innerhalb der Instanz selbst gibt es diese Einschränkung nicht

##  Wo sollte man Custom Actors nicht einsetzen?

- Als ViewModel - hier sollte man mit `@MainActor` arbeiten, da die Änderungen ja auf dem Main-Thread geschehen sollen.

##  Zusammenfassung
- Zweck
- Code
- Was ist Actor Isolation?
- Wo sollte man Custom Actors nicht einsetzen?

#learning unit#