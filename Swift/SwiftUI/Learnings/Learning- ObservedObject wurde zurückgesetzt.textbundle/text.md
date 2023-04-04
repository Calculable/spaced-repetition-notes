# Learning: ObservedObject wurde zurückgesetzt
🧠

## Der Fehler war im folgenden Codebeispiel (Konzept)

###  Model
```swift
@MainActor class MyModel: ObservableObject {

	@Published...
	
}
```


### Im View

```swift
//...
.sheet(isPresented: $showSheet) {
	MyDetailView(model: MyModel())
}
```

### Im Inhalt des Sheets

```swift
@ObservedObject var myModel: MyModel
//...
```

## Problem

Wenn ich im Sheet ein Alert angezeigt habe, dann wurden die Werte im Model zurückgesetzt.


## Lösung

Im Sheet musste ich stattdessen verwenden:

```swift
@StateObject var myModel: MyModel
//...
```

=\> Denn ansonsten hat man ja nur ObservedObject, ohne dass man irgendwo ein StateObject hat.

Alternativ könnte ich natürlich auch das neue Model mit `@StateObject` direkt innerhalb der Sheet-View erstellen

## Zusammenfassung
- Was war das Problem und was die Lösung


#learning unit#