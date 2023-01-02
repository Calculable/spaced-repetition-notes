
# JPA / Spring Data / Repository / Hibernate 💿

##  Unterschiede

**JPA**: Ist nur eine Spezifikation

**Spring Data**: Baut auf JPA auf. Ein Framework für einfachen Datenzugriff mit weiteren Methoden. Implementiert selbst keine Funktionalität sondern benötigt eine JPA Implementation wie Hibernate, jdbc etc.

Hibernate: Implementiert die JPA-Spezifikation. 

##  Zwei Arten des Loadings
- Lazy loading
- Eager Loading

## Repositories

- Das Repository macht man entweder Manuell:

```swift
currentSession().createCriteria(Splitter.class).list
```

oder automatisch

```swift
interface XY extends CrudRepository<Car, Integer>
```


##  Zusammenfassung
- Unterschiede
- Zwei Arten des Loadings
- Zwei Arten um repositories zu implementieren