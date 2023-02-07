
# Chain of Responsibility
🪖


>  This pattern decouples sender and receiver of a request based on type of request.

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

#nur learning unit#