# Initializer Inheritance
🛫

Nur in den folgenden zwei sicheren Fällen werden die Initializer der Oberklasse geerbt:

1. Wenn die Subklasse keinen designated initializer hat, dann erbt es alle designated initializer

2. Wenn die Subklasse alle designated initializer überschreibt (oder erbt durch Punkt 1), dann erbt es auch automatisch alle convenience initializer der Superklasse

## Zusammenfassung
- In welchen zwei Fällen werden Initializer vererbt?


#learning unit#