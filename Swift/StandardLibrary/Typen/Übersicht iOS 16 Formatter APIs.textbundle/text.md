# Übersicht iOS 16 Formatter APIs
⚙️

## Wie funktionieren die APIs?
Neu kann man auf diversen Datentypen `.formatted(...)` aufrufen:


##  Beispiele

### Bytecount

```swift
let severalTerabytes = Measurement(value: 3, unit: UnitInformationStorage.terabytes)

severalTerabytes.formatted() // "3 TB"
severalTerabytes.formatted(.byteCount(style: .binary)) // "2.73 TB"
```


```swift
let weight = Measurement(value: 20, unit: UnitLength.centimeters)
return weight.formatted()
```

###  Duration

```swift
let thousandSeconds: Duration = .seconds(1000)

thousandSeconds.formatted() // "0:16:40"
thousandSeconds.formatted(.time(pattern: .hourMinute)) // "0:17"
```

###  Number

```swift
let number = 3.147
      let numString = number.formatted(.number.precision(.fractionLength(2)).rounded(rule: .up))
      // 3.15
```

Siehe: [ulysses://x-callback-url/open?id=IQ9eA7tZG9ue1ISan86-aQ][1]
###  List

```swift
let numString1 = numberlist.formatted(
            .list(
                memberStyle: .number.precision(.fractionLength(2)).rounded(rule: .up),
                type: .and
            )
        )
    // 3.35, 534.35, and 4,546.43
```

### Date

```swift
let dateString = Date.now.formatted(.iso8601.year().month().day().dateSeparator(.dash).dateTimeSeparator(.space).time(includingFractionalSeconds: false) .timeSeparator(.colon))

```

Siehe: [ulysses://x-callback-url/open?id=tEIz2DVcLaFPofUzGd3r9g][2]


### PersonNameComponents

```swift
var components = PersonNameComponents()
components.givenName = "Taylor"
components.middleName = "Alison"
components.familyName = "Swift"
components.nickname = "Taytay"

print("Short: \(components.formatted(.name(style: .abbreviated)))") //TS
```

Siehe: [ulysses://x-callback-url/open?id=QEYwmD3NTRL4UfRiwywiyw][3]

##  Zusammenfassung
- Wie verwendet man die iOS 16 Formatter API? (nur die Funktion)

[1]:	ulysses://x-callback-url/open?id=IQ9eA7tZG9ue1ISan86-aQ
[2]:	ulysses://x-callback-url/open?id=tEIz2DVcLaFPofUzGd3r9g
[3]:	ulysses://x-callback-url/open?id=QEYwmD3NTRL4UfRiwywiyw

#learning unit#