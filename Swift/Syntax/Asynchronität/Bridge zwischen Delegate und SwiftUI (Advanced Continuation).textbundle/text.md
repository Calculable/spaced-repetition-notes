# Bridge zwischen Delegate und SwiftUI (Advanced Continuation)
🌉

## Siehe auch

Kapitel: Continuation


## Problem

- Häufig hat man nicht nur einfach eine einzelne Callback-Funktion, die man durch eine Continuation ersetzen könnte sondern ein ganzes Delegate mit mehreren Funktionen.
- Man kann nicht eine SwiftUI-Klasse zu einem Delegate machen, weil es ein Struct ist statt eine Klasse

## Frühere Lösung

Deshalb hat man oft eine eigene Klasse gemacht

```swift
class AsyncFileDownloader: MyNetworkManagerDelegate, ObservableObject {
    let networkManager: NetworkManager
    let url: URL

    var success: ((Data) -> Void)?
    var failure: ((Error) -> Void)?

    init(url: URL) {
        self.url = url

        networkManager = NetworkManager(url: url)
        downloader.delegate = self
    }

	//Hier werden die Closures entgegengenommen
    func download(success: @escaping (Data) -> Void, failure: @escaping (Error) -> Void) {
        self.success = success
        self.failure = failure

        networkManager.start()
    }

	//delegate funktionen
    func didSucceed(data: Data) {
        success?(data)
    }

    func didFail(error: Error) {
        failure?(error)
    }
}
```

Jetzt kann man es so aufrufen:

```swift
ScrollView {
	Text(string)
}
.task {
	downloader.download { data in
		string = String(decoding: data, as: UTF8.self)
	} failure: { error in
		string = error.localizedDescription
	}
}
```


##  Heute: Advanced Continuation

Der Typ einer Continuation ist zum Beispiel: `UnsafeContinuation<[Int], Error>`


```swift
class AsyncFileDownloader: MyNetworkManagerDelegate, ObservableObject {
    private let networkManager: NetworkManager
    private let url: URL

    private var continuation: CheckedContinuation<Data, Error>?

    init(url: URL) {
        self.url = url

        networkManager = NetworkManager(url: url)
        downloader.delegate = self
    }

    func start() async throws -> Data {
        try await withCheckedThrowingContinuation { continuation in
            self.continuation = continuation
            networkManager.start()
        }
    }

	//delegate funktionen
    func didSucceed(data: Data) {
        continuation?.resume(returning: data)
    }

    func didFail(error: Error) {
        continuation?.resume(throwing: error)
    }
}
```

Innerhalb der SwiftUI View:

```swift
.task {
    do {
        let data = try await downloader.download()
        string = String(decoding: data, as: UTF8.self)
    } catch {
        string = error.localizedDescription
    }
}
```

## Vorteile
- Man verwendet das Concurrency System
- man kann mit `do/catch` arbeiten.

## Zusammenfassung
- Welche zwei Varianten können verwendet werden, um ein Delegate gemeinsam mit SwiftUI zu verwenden (eine Lösung ohne Async-Await, die andere mit)
- Primär Konzept und Vorteile, weniger Code

#learning unit#