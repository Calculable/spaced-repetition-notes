# Javascript Einfache Klasse 🚙

```java
class einfachesMathe {
  constructor(zahlEins, zahlZwei) {
    this.zahlEins = zahlEins;
    this.zahlZwei = zahlZwei;
  }
  addieren(){
    return this.zahlEins + this.zahlZwei;
  }
  get addition(){
    return this.addieren();
  }
}
var aufgabe = new einfachesMathe(2, 5);
console.log(aufgabe.addition);
// 7
```

## Zusammenfassung
- Beispielcode mit Konstruktor, Funktion und Getter