# UIView Autolayout Pass
🔁
1. **(Init)**
2. **Update**
	- Siehe Kapitel `updateConstraints` (hier wird das View-Frame berechnet, basierend auf den Subviews, Bottom-Up)
3. **Layout**
	- Siehe Kapitel `layoutSubviews`
4. **Render** (wird mit einem CALayer gemacht -\> Bitmap)
	- `drawRect` muss man in der Regel nicht überschreiben wenn man eine View aus anderen Views zusammensetzt oder Standart-Optionen wie den Hintergrund verändert =\> nur für Custom Drawing benötigt


## Zusammenfassung
- Welche 4 Autolayout Phasen gibt es?
- Welche Methode ist wichtig pro Phase?

#learning unit#