
# Spring Unit Test ☑️

- **JUnit**
	- Um tests auszuführen und das Resultat zu prüfen
	- Eher ein generelles Testing-Framework (man nimmt sonst eher Spring test)
- **AssertJ**
	- Wird oft mit JUnit zusammen eingesetzt
- **Spring Test**: 
	- Support um Spring-Applikationen zu Testen
		- Testen von Komponenten
		- Applikationskontext Laden
		- Dependency Injection
	- Test Methoden ausführen
	- Man braucht damit JUnit eigentlich nicht mehr, JUnit Annotationen werden aber unterstützt
- **Mockito**
	- Simuliert die Objekte
	```swift
	when(mockRepository.findSpittles(Long.MAX_VALUE, 20))
		.thenReturn(expectedSpittles);
	```

##  Zusammenfassung
- Was macht JUnit, AssertJ, Spring Test, Mockito…?

#nur learning unit#