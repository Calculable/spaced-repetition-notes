
# Singleton
🍷

## Zweck

- Von einer Klasse sollte es nur eine Instanz geben
- z.B. für geteilte Ressourcen

## Implementierung

- Default Contructor Private machen, damit man nicht darauf zugreifen kann
- Eine Statische Methode machen, die als Konstruktor agiert und prüft, b bereits eine Instanz vorhanden ist

## Beispiel

```swift
import XCTest


class Singleton {

    static var shared: Singleton = {
        let instance = Singleton()
        // ... configure the instance
        // ...
        return instance
    }() //beachte - das ist nicht ein generated getter sondern das Property wird genau einmal zugewiesen

    private init() {} //private initializer

    func someBusinessLogic() -> String {
        //...
    }
}

/// Singletons should not be cloneable.
extension Singleton: NSCopying {
    func copy(with zone: NSZone? = nil) -> Any {
        return self
    }
}


class Client {
	let instance1 = Singleton.shared
	//...    
}

```

## Zusammenfassung
- Zweck
- Beispielcode

#nur learning unit#