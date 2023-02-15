# CoreData inverse Beziehungen
🧑‍🤝‍🧑

## Was sind inverse Beziehungen?
- In Core Data kann man inverse Beziehungen definieren.
- Beispiel: Ein Projekt hat viele Items und ein Item hat ein Projekt.
- In der generierten Klasse hat man dann sowohl im Projekt ein Set mit Items und auch in jedem Item eine Referenz auf das Projekt

## Man muss immer nur eine der beiden Seiten aktualisieren.

-\> Die andere Seite wird von CoreData selbst angepasst.

```swift
item.project = project
```

=\> Im Project muss man jetzt nicht mehr das Item zuweisen.

## Was sollte man nicht tun?
Hinweis: Core-Data generiert extra Methoden, zum Beispiel ein Element zu einer To-Many beziehung hinzuzufügen. Man sollte als in diesem Beispiel nicht von Hand ein neues Item zum items-Array im Projekt hinzufügen, sondern die Hilfsmethode verwenden.

## Zusammenfassung
- Was ist eine inverse Beziehung?
- Inwiefern erleichtert CoreData die arbeit mit inversen Beziehungen?
- Was sollte man nicht tun?


#nur learning unit#