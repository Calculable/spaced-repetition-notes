# DDL (Data Definition Language) 🏛️

```sql
CREATE TABLE Projekt (
	ProjNr INTEGER PRIMARY KEY, -- beachte Primary Key
	Bezeichnung VARCHAR(20) NOT NULL UNIQUE, -- beachte: Not Null Unique
	StartZeit DATE NOT NULL DEFAULT CURRENT_DATE, -- beachte Default
	Dauer INTEGER NULL CHECK (DAUER BETWEEN 10 AND 100), -- beachte Check. Null ist sowieso default
	ProjLeiter REFERENCES ANGESTELLTER ON DELETE SET NULL --beachte Reference und ON Delete
	-- etc.
);
```

## Zusammenfassung
- Beispiel: Tabelle mit mehreren Attributen