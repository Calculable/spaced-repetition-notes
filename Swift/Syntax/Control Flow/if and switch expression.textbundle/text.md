# if and switch expression
🔀

## Beispiel mit if

```swift
let bonusMultiplier2 = if customerRating > 3 { 1.5 } else { 1.0 }
```

## Beispiel mit switch

`
````swift
func rating(for score: Int) -> String {
    switch score {
    case 0...300: "Fail"
    case 301...500: "Pass"
    case 501...800: "Merit"
    default: "Distinction"
    }
}
```

(Beachte: hier braucht man kein Return-Keyword, weil es nur ein einziges Statement ist)


## Zusammenfassung
- Was ist damit gemeint
- Beispiel If
- Beispiel Switch

#learning unit# #Swift5.9#