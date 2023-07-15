# TLS/SSL Pinning
📌

- Man hardcoded das Server-Zertifikat in die App
	- Das Zertifikat sollte dabei regelmässig erneuert werden (z.B. mit jedem Release)
- Wenn jemand über ein Proxy die Antworten des Servers verändert, dann kann der Client die Verbindung abbrechen
- Diese Methode ist jedoch nicht 100% sicher und kann durchbrochen werden
- Einen zusätzlichen Sicherheitslayer bieten z.B. Themis, Secure Session, libsodium, noise protocol…


##  Zusammenfassung
- Wozu ist das sinnvoll?

#learning unit#