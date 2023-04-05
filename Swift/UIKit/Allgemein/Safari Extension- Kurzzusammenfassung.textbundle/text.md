# Safari Extension: Kurzzusammenfassung
🧩

## Allgemein
- Es braucht eine Shell App
- Es braucht ein eigenes Target: **Action Extension**
- In der Plist kann man steuern, in welchen Kontexten die Extension verfügbar sein soll
- Neben Safari Extensions gibt es natürlich auch noch ganz andere Extensions

## Zwischenschicht

Für Safari braucht man ein Javascript File

```js
var Action = function() {};

Action.prototype = {

run: function(parameters) {
	//Informationen aus Webseite auslesen und an Swift übergeben
},

finalize: function(parameters) {
	//Informationen von Swift erhalten und Webseite entsprechend manipulieren
}

};

var ExtensionPreprocessingJS = new Action
```

## Zusammenfassung
- Wie wird eine Extension konfiguriert
- Wie werden Daten zwischen einer Webseite und Swift hin- und hergegeben?

#learning unit#