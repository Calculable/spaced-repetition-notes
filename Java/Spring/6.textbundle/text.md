
# Spring Resource Abstraction 📑

Dank Spring Resource Abstraction braucht man deutlich weniger Boilerplate Code

```swift
Resource aFileTemplate = ctx.getResource("file:///someDirectory/application.properties"); // (3)

Resource anHttpTemplate = ctx.getResource("https://marcobehler.com/application.properties"); // (4)

Resource aClasspathTemplate = ctx.getResource("classpath:somePackage/application.properties"); // (2)

```


##  Zusammenfassung
Um was geht es?

