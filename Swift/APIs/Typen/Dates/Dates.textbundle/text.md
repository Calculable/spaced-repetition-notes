# Dates

## Aktuelles Datum
```swift
let now = Date.now
```

## Time Interval addieren

```
let tomorrow = Date.now.addingTimeInterval(86400)
```

## Date Range

```
let range = now...tomorrow
```

## Ein Datum erstellen
```swift
var components = DateComponents()
components.hour = 8
components.minute = 0
let date = Calendar.current.date(from: components) //gibt ein Optional zurück
```

## Ein Datum lesen
```swift
let components = Calendar.current.dateComponents([.hour, .minute], from: someDate)
let hour = components.hour ?? 0
let minute = components.minute ?? 0
```

## Formatieren
```swift
Text(Date.now, format: .dateTime.hour().minute())
```

```swift
Text(Date.now.formatted(date: .long, time: .shortened))
```

> You might wonder how that adapts to handling different date formats – for example, here in the UK we use day/month/year, but in some other countries they use month/day/year. Well, the magic is that we don’t need to worry about this: when we write day().month().year() we’re asking for that data, not arranging it, and iOS will automatically format that data using the user’s preferences.



#guide