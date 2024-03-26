# Task Gruppe
👨‍👩‍👧‍👦

##  Zweck

- Mehrere Tasks, die gemeinsam einen einzigen Wert produzieren

## Codebeispiel mit Reduce

```swift
await withTaskGroup(of: Int.self) { group -> Int in
        
    for i in 0..<10{
        group.addTask {
            let from = //...
            let to = //...
            return await countPrimeNumbers(range: from...to)
        }
    }
    
    return await group.reduce(0, (+))
}
```


## Codebeispiel mit warten auf einzelne Werte

### Code
```swift
for await value in group {
	collected.append(value)
}
```

###  Reihenfolge der Resultate

- Die Reihenfolge wird bestimmt durch die „completion order“ und nicht die „creation order“


##  Mit Throwing Tasks arbeiten

Hier verwendet man `withThrowingTaskGroup()`


## Zusammenfassung
- Zweck
- Codebeispiel mit Reduce

#learning unit#