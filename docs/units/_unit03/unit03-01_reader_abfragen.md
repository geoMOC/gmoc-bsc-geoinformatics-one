---
title: Fragen & Antworten 
toc: true
toc_label: Inhalt


---


Die Datenbankstruktur der meisten GI-Systeme stellt eine logische, konsistente und strukturierte Speicherung und Verwaltung der Daten in Form von sogenannten Relationen dar. In solchen Relationen (auch Tabellen genannt) liegen sowohl geometrische als auch semantische (thematische) Daten in tabellarischer Form vor.<!--more-->  Der wohl wichtigste Aspekt eines GI-Systems ist die Datenanalyse, also die Durchführung von gezielten Abfragen und Auswertungen auf die in den Tabellen vorliegenden räumlich-inhaltlichen Daten. Datenanalysen werden mit Hilfe von einer Abfragesprache der *Structured Query Languange* (SQL) als Abfragen auf die Grundelemente der Relationen (Tabelle, Feld, Datensatz, Wert und Assoziation) durchgeführt und in Aussagen überführt.

Beispiel einer Abfrage:

*"Wie groß ist der prozentuale Anteil der Marburger Stadtbevölkerung, der mehr als 200 m von einer Haltestelle des ÖPNV entfernt wohnt?"*

## Die Lernziele des Readers sind:

  * thematische, geometrische und topologische Abfragen unterscheiden zu können
  * thematische geometrische und topologische Abfragen durchführen zu können


## Abfragen in Relationen – eine Einführung
	

Im Rahmen der Datenanalyse sind prinzipiell drei Ansätze (vgl. Abbildung 03-01) möglich:

  * *Thematische Abfragen:* Selektiert die Objekte, deren Eigenschaften (Attribute) die gestellten Bedingungen erfüllen – z. B.: „Selektiere alle Bäume der Art Fichte.“
  * *Geometrische Abfragen:* Selektiert die Objekte, welche die gestellten räumlichen Bedingungen erfüllen z. B.: „Selektiere alle Häuser, die weniger als 250 m vom Fluss entfernt sind.“
  * *Topologische Abfragen:* Selektiert die Objekte, welche die gestellten Bedingungen bezüglich den räumlichen Beziehungen zwischen den Objekten erfüllen - z. B.: „Selektiere alle Gebäude, die vollständig in der Wohnzone II (WII) liegen.“
  
{% include figure image_path="http://gisbsc.gis-ma.org/GISBScL6/de/image/abfrage2.jpg" alt="Gliederung der nicht-manipulativen GI-Abfragen" caption="*Abbildung 03-01: Gliederung der nicht-manipulativen GI-Abfragen (GITTA 2005)*" %}



## Auswahloperatoren

Zentrales Hilfsmittel von Abfragen an GI-Systemen sind sogenannte Auswahloperatoren, auch algebraische Operatoren genannt. Sie gliedern sich in:

  * *Vergleichende Operatoren:* Für die Formulierung von Fragen können neben dem Gleichheitszeichen auch Vergleichsoperatoren verwendet werden.
  * *Arithmetische Operatoren:* Diese Operatoren werden für numerische Attribute verwendet, z. B. können aus einer Reihe ausgewählter Objekte Mittelwerte von einem Attribut, Summen von Attributwerten usw. berechnet werden.
  * *Logische Operatoren:* Mit logischen Operatoren werden Bedingungen formuliert.

### Vergleichsoperatoren

Die Vergleichsoperatoren können für unterschiedlich skalierte Attribute (Zahlen, Text) verwendet werden. Bei nicht numerischen Attributen beziehen sich Vergleiche „größer als“, „kleiner als“ usw. auf die Position in einer internen vom Computer verwendeten „alphabetischen“ Ordnung (z.B. ASCII-Code Tabelle).

| Vergleichende Operatoren | Bedeutung |   
| =    | EQ (gleich)                   |
| >    | GT (größer)                   |    
| >=   | GE (größer gleich)            | 
| <    | LT (kleiner)                  |    
| < =   | LE (kleiner gleich)          | 
| <>   | NE (ungleich)                 |    

*Tabelle 03-01: Vergleichende Operatoren*

### Arithmetische Operatoren

Die arithmetischen Operatoren werden für numerische Attribute verwendet, z. B. können aus einer Reihe ausgewählter Objekte Mittelwerte von einem Attribut, Summen von Attributwerten usw. berechnet werden. Als arithmetische Operatoren können der Multiplikations- `*`, der Divisions- `/`, der Additions- `+` und der Subtraktionsoperator `-`, der Exponent `exp` sowie der Modulo-Operator `%` verwendet werden. Die Modulo-Operation liefert den Rest einer ganzzahligen Division (z.B.`5 % 2 = 1`)

### Logische Operatoren

Logische Operatoren verbinden Attribute oder Teilabfragen als logische Ausdrücke (mit den zwei möglichen Werten „wahr“ oder „falsch“). Sie eigenen sich daher für eine effiziente Gestaltung komplexer Abfragen. Die logischen Operatoren werden auch Boolesche Algebra genannt. Sie basiert auf der binären Struktur, die auf den Werten 1 (wahr) und 0 (falsch) beruht. Dazu bietet sie eine Reihe verschiedener Verknüpfungen, die „wahr“ oder „falsch“ sein können, nie aber beides. Die in GIS für die Verknüpfung von zwei räumlichen Auswahlkriterien verwendeten Booleschen (oder logischen) Operatoren sind `AND`, `OR`, `XOR` und `NOT`: Die nachfolgende Tabelle listet die 4 logischen Grundoperatoren und Ihre Wirkungsweise auf:

Zur Verdeutlichung sind in der rechten Spalte die *Venn-Diagramme* der Booleschen Operatoren dargestellt. Die Darstellung wird verständlicher wenn man sich vorstellt, dass  Kreis 1 und Kreis 2 jeweils graphisch zwei Bedingungen (oder Untermengen der Relation) darstellen. Konkret Kreis 1: GEBIET = „bewaldet“ und Kreis 2: GEBIET = steil. Die schraffierte Fläche repräsentiert jeweils die wahre Aussage. In dieser Grundform entspricht der Teil außerhalb der Kreise keinem Abfrageresultat.

{% include figure image_path="/assets/images/unit03/combination.jpg" alt="Die vier Boolschen Operatoren (GITTA 2005)" caption="Die vier Boolschen Operatoren (GITTA 2005)" %}


In vielen GIS-Programmen entsprechen die Booleschen Operatoren direkt aufrufbaren Funktionen und tragen oft vergleichbare Namen. So entspricht in vielen GIS-Programmpaketen die Funktion `INTERSECT` dem `AND`, `UNION` dem `OR` und `ERASE` dem `NOT` Operanden. Die letzte Funktion wird auch sehr anschaulich „*cookie cutting*“ genannt, weil die Form des zweiten Kriteriums wie beim Plätzchen-Backen aus dem ausgerollten Teig des ersten „*ausgestochen*“ wird.

### Kombination der Operatoren

Durch die Kombination von Operatoren ist es möglich mehrere Bedingungen zu verknüpfen. Allerdings sind Boolesche Operatoren **nicht** kommutativ, d. h. das Ergebnis ihrer Anwendung in komplexen Ausdrücken hängt von der definierten Reihenfolge der Teilausdrücke ab. Betrachten Sie die nachfolgenden Beispiele und versuchen Sie anhand Ihrer bisherigen Kenntnisse die Abfragen mit ihren Komponenten nachzuvollziehen.

	 
<html><a href="https://www.flickr.com/photos/environmentalinformatics-marburg/14161471688" title="06-03-01 by Environmental Informatics Marburg, on Flickr"><img src="https://farm3.staticflickr.com/2922/14161471688_12d9ff0432_o.png" width="983" height="500" alt="06-03-01"></a></html>
<html><a href="https://www.flickr.com/photos/environmentalinformatics-marburg/14348127685" title="06-03-02 by Environmental Informatics Marburg, on Flickr"><img src="https://farm3.staticflickr.com/2913/14348127685_0ed1e5b815_o.png" width="936" height="536" alt="06-03-02"></a></html>	 	 

//Abbildung 07-03:  Kombination der Operatoren. THEM = Thematische Abfrage, GEOM = Geometrische Abfrage und TOPO = Topologische Abfrage (GITTA 2005)//


## Denken Sie mit...

  * Warum ist eine Unterscheidung in vergleichende, arithmetische und logische Operatoren Ihrer Meinung nach sinnvoll?
  * Können Sie noch spontan den Unterschied zwischen “ist gleich” ( = ) und logischem UND erläutern?

