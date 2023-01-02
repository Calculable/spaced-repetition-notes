
# Visitor 👋

## Problem: Double-Dispatch

Wir können nicht folgendes schreiben:

```java
class XMLSerializer implements SerializerVisitor { 
	public void serialize(CompositeNode node);
	public void serialize(LeafNode leafNode);
}
```

Problem: Wenn man `serialize()` aufruft und als Parameter eine `CompositeNode ` übergibt, die aber in einer Variable vom Typ `Node` gespeichert ist, dann ist unklar, welche Methode genommen wird.


## Lösung

Jede Node implementiert die `accept(SerializerVisitor)` Funktion.

Zum Beispiel die LeafNode:
```java
@Override
	public void accept(SerializerVisitor visitor) {
		visitor.visitLeafStart(this);
		visitor.visitLeafEnd(this);
	}

```

Oder die CompositeNode:
```java
@Override
	public void accept(SerializerVisitor visitor) {
		visitor.visitCompositeStart(this);
		getChildren().forEach((c) -> c.accept(visitor));
		visitor.visitCompositeEnd(this);
	}

```

Beachte: Auf dem Serializer-Visitor werden jetzt konkrete Funktionen für die einzelnen Typen aufgerufen.

Beachte: Statt einem XML-Serialisierer könnte man auch einen anderen Serialisierer implementieren

## Vorteile
- Der Besuchte muss den Besucher nicht kennen
- Neue Operationen können einfach hinzugefügt werden

## Zusammenfassung
- Zweck
