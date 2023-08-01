# Capture Value vs. Capture Variable
🦋

## Capture Variable

Dieser Code gibt „2“ aus:

```swift
var myVariable = 1

let closure = {
    print(myVariable)
}

myVariable = 2

closure() //2
```


## Capture Value

Dieser Code gibt „1“ aus: 

```swift
var myVariable = 1

let closure = { [myVariable] in
    print(myVariable)
}

myVariable = 2

closure() //1
```

##  Zusammenfassung
- Was ist der Unterschied? (Syntax)

#learning unit#