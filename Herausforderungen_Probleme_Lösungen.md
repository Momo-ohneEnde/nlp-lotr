# Herausforderungen, Probleme und Lösungen beim NLP-Projekt

## Datenbereinigung

### 1. Trennung von Regieanweisungen und Sprechertext
* unterschiedliche Kennzeichnung von Regieanweisungen in den verschiedenen Skripten (1 und 3 - Blöcke ohne Whitespace, 2 - eckige Klammern)
* Skripte 1 und 3: Regieanweisungen stehen z.T. direkt nach dem Sprechertext -> können nicht automatisiert extrahiert werden, Liste erstellen mit allen Regieanweisungen in Sprechertexten, bei jedem Sprechertext-Block wird überprüft ob eine der Regieanweisungen aus der Liste drin vorkommt
* Skripte 1 und 3: viel überflüssige Texte dabei (Seitenzahlen, Continued-Angaben, Kamerapositionen etc.) -> müssen gelöscht werden
* Skripte 1 und 3: Großschreibung z.T. zur Hervorhebung von Namen, wichtigen Passagen etc. verwendet

### 2. Encoding-Fehler und andere Fehler auf Zeichenebene
* willkürlich Leerzeichen zwischen Worten, Bsp: "PIPPIN has jumped off his ho rse an d pi cke d u p -- th e PA LAN TIR" -> manche können über gezieltes ersetzen abgefangen werden, aber nicht alle
* Encodingfehler mit ?-Symbol -> mussten alle einzeln ersetzt werden
* falsche Wörter: Gandalf ignOrcs the children's cries.

### 3. Passagen auf Elbisch und anderen Lotr-Sprachen
* Übersetzte Passagen übernehmen, aber elbischen Text löschen

### 4. Durch ... getrennte Sätze zusammenführen

## NLP Analyse