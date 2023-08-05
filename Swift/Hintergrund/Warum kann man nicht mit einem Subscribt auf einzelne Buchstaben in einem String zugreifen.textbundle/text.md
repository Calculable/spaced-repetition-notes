# Warum kann man nicht mit einem Subscribt auf einzelne Buchstaben in einem String zugreifen?
💡

- Theoretisch könnte Apple diese Option anbieten
- Sie machen es aber nicht, um zu zeigen dass das sehr unperformant wäre
- Weil jedes Zeichen im Speicher unterschiedlich viel Platz benötigt, müsste man dazu durch den ganzen String iterieren um zur richtigen Stelle zu gelangen.
- Grund dafür ist, dass einige Symbole (z.B: Emojis) aus mehreren Unicode-Zeichen zusammengesetzt werden.
- Bei einem normalen Array hingegen lässt sich die Speicherposition anhang des Indexes berechnen

#learning unit#