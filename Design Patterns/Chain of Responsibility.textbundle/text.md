
# Chain of Responsibility
🪖

> The Chain of Responsibility is a behavioral design pattern that allows an object to pass along a request to a chain of potential handlers until it is processed by one of them.

> Each handler decides whether it can process the request. If it can, it does so and returns, stopping the chain. If it cannot, it passes the request to the next handler in the chain.

## Beispiel
(Finde das Beispiel nicht ganz gelungen)
![][image-1]

- Man will Dinge eventuell mehrfach loggen und hängt deshalb mehrere Logger zusammen
- Jeder AbstractLogger hat eine Referenz auf den nächsten Logger, also ConsoleLogger -\> ErrorLogger -\> FileLogger

Aufruf: 

```java
loggerChain.logMessage(AbstractLogger.INFO, 
         "This is an information.");
```


## Zusammenfassung
- Zweck

[image-1]:	https://www.tutorialspoint.com/design_pattern/images/chain_pattern_uml_diagram.jpg

#learning unit#