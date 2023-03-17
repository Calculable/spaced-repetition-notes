# Core Data best practice: Wann sollte man die Daten speichern?
🤔

- Häufiges Speichern mit Core Data ist schlecht für die Performance

> Apple does have some official guidance here, when talking about apps being moved to the background: “If your app has unsaved user data, you can save it to ensure that it isn’t lost. However, it is recommended that you save user data at appropriate points throughout the execution of your app, usually in response to specific actions.”


Konkret heisst das zum Beispiel: Wenn man einen Edit-Dialog hat, und mit Bindings arbeitet, sollte man nicht bei jeder Änderung die Dateien mit `managedObjectContext.save()` speichern. Stattdessen kann man die Daten dann speichern, wenn der Dialog geschlossen wird.


## Zusammenfassung
- Wie häufig sollte man `ManagedObjectContext` von Core Data speichern?

#learning unit#