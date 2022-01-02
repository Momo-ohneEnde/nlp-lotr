# Herausforderungen, Probleme und Lösungen beim NLP-Projekt

## Datenbereinigung

### 1. Trennung von Regieanweisungen und Sprechertext
* unterschiedliche Kennzeichnung von Regieanweisungen in den verschiedenen Skripten (1 und 3 - Blöcke ohne Whitespace, 2 - eckige Klammern)
* Skripte 1 und 3: Regieanweisungen stehen z.T. direkt nach dem Sprechertext -> können nicht automatisiert extrahiert werden, Liste erstellen mit allen Regieanweisungen in Sprechertexten, bei jedem Sprechertext-Block wird überprüft ob eine der Regieanweisungen aus der Liste drin vorkommt
* Skripte 1 und 3: viel überflüssige Texte dabei (Seitenzahlen, Continued-Angaben, Kamerapositionen etc.) -> müssen gelöscht werden, aber sehr schwer alle automatisiert ausfindig zu machen, weil a) nicht alle vor einem Doppelpunkt stehen b) viele verschiedene Schreibweisen für dieselbe Anweisung verwendet werden z.B. Slow motion, SLOW MOTION und c) es sehr viele verschiedene Kamera-Anweisungen gibt
* Skripte 1 und 3: Großschreibung z.T. zur Hervorhebung von Namen, wichtigen Passagen etc. verwendet
* Skripte 1 und 3: Auslassungspunkte (...) werden sehr häufig verwendet, aber nicht einheitlich. Manchmal stehen sie mitten in einem Satz, machmal ersetzen sie am Ende eines Satzes den Punkt. Zusätzlich werden verschiedene Varianten von Auslassungspunkten verwendet und eine unterschiedliche Anzahl von Punkten. Keine einheitliche Lösung möglich. Lösungsansatz: Auslassungspunkte innerhalb eines Blocks/einer Zelle durch Leerzeichen ersetzen. Auslassungspunkte am Anfang oder Ende eines Blocks/einer Zelle durch einen Punkt ersetzen.

### 2. Encoding-Fehler und andere Fehler auf Zeichenebene
* willkürlich Leerzeichen zwischen Worten, Bsp: "PIPPIN has jumped off his ho rse an d pi cke d u p -- th e PA LAN TIR" -> manche können über gezieltes ersetzen abgefangen werden, aber nicht alle
* Encodingfehler mit ?-Symbol -> mussten alle einzeln ersetzt werden
* falsche Wörter: Gandalf ignOrcs the children's cries.

### 3. Passagen auf Elbisch und anderen Lotr-Sprachen
* Übersetzte Passagen übernehmen, aber elbischen Text löschen

### 4. Durch ... getrennte Sätze zusammenführen
nur in Dialogtexten möglich

in Regieanweisungstexten: unmöglich automatisiert herauszufinden, ob die Auslassungspunkte innerhalb eines Satzes stehen (und somit durch ein Leerzeichen ersetzt werden müssen) oder einen Satz abschließen (also durch einen Punkt ersetzt werden müssen)

## NLP Analyse