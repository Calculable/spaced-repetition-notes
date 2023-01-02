# Polymorphismus,  Liskov Substitution Principle, Dynamic Dispatch 🎭

##  Polymorphismus

Ein Objekt hat nicht nur den Typ seiner Klasse, sondern auch die Typen seiner Superklassen

```java
Car c = new Car();
Vehicle v = new Car();
Object o = new Car();
```

##  Liskov Substitution Principle

Objekte einer Klasse soll man durch Objekte einer Subklasse ersetzen können, ohne die Programm-Korrektheit zu verletzen.

Dass heisst, ich kann einer Methode, die ein „Vehicle“ entgegennimmt, einen „Car“ geben.

## Dynamic Dispatch

Es wird zur Laufzeit die Methode gewählt, die ausgeführt wird

```java
Vehicle vehicle = new Car();
vehicle.report();
```

Erzeugt die Ausgabe:

```
«This is a car»
```


## Zusammenfassung
Was bedeuten die drei Begriffe?