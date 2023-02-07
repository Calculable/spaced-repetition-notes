# Dates / Calendars
📅

##  Date
- Date ist ein bestimmter Zeitpunkt
- Das Date weiss nicht zu welcher Zeitzone es gehört

```swift
let date = Date(timeIntervalSinceReferenceDate: 123456)
```

## Calendar
- Calendar wird genutzt, um operationen an Dates vorzunehmen (Time Intervalle addieren, Time in verschiedene Zeitzonen konvertieren etc.)

```swift
let calendar = Calendar.current
```

> For example, if you wanted to find the difference between two dates in terms of days, you might assume that you could simply subtract the two dates and divide by the number of seconds in a day. However, this approach would not take into account the fact that different calendars have different numbers of days in a year, or that some calendars have leap years.


## Zusammenfassung
- Zweck und Unterschied von Date / Calendar