# Capture Value vs. Capture Variable
🦋

## Capture Variable

Dieser Code gibt „2“ aus:

```swift
var myVariable = 1

let closure = {
    print(myVariable) //myvariable ist eine veränderbare referenz (obwohl es ein primitiver value-type ist)
}

myVariable = 2

closure() //2
```


## Capture Value

Dieser Code gibt „1“ aus: 

```swift
var myVariable = 1

let closure = { [myVariable] in
    print(myVariable) //myvariable ist eine unveränderbare kopie
}

myVariable = 2

closure() //1
```

##  Praxisbeispiel
Siehe: [ulysses://x-callback-url/open?id=zEFSyIuh5G0RF-r-mA7gdw][1]

##  Zusammenfassung
- Was ist der Unterschied? (Syntax)

[1]:	ulysses://x-callback-url/open?id=zEFSyIuh5G0RF-r-mA7gdw

#learning unit#