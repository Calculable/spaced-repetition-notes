# Protokollanforderungen für id: \\.self 👤

- Wenn die Elemente das `Identifiable` Protokoll implementieren, dann braucht man `id: \.self` nicht
- Bei einem Struct wird bei `\.self` der Hashwert über alle Properties gebildet, wenn es nicht Identifiable ist (dazu muss es Hashable sein)

##  Zusammenfassung
- Wann kann man eine Sequenz mit ForEach und id: \\.self verwenden?