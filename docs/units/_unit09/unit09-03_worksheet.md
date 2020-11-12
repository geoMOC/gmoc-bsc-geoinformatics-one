---
title: Lerneinheit 3 - Fragen & Antworten
toc: true
header:
  image: /assets/images/01-splash.jpg
  image_description: "John Snows "
  caption: "Map: [**Dr. John Snow**](https://de.wikipedia.org/wiki/John_Snow_(Mediziner)) [Wellcome Library via wikimedia](https://w.wiki/QtV)"

---


Das systematische Abfragen von Datenbankinhalten sind Sie aus dem Alltag gewöhnt. Sei es die Abfrage von Zugverbindungen, Kinokarten die Sie online bestellen  oder die Suchanfrage bei Google. <!--more-->
Auch die Integration räumlicher Abfragen ist Alltag für Sie. Falls sie zb. die Location based Services in Google aktiviert haben werden Sie regelmäßig mit lokalisierter Werbung oder Abstimmungsanfragen bedacht. Doch wie können sie solche Abfragen selber gestalten und was sind die Prinzipien die zum Tragen kommen?

## Was wir in dieser Einheit vor haben
In dieser Lerneinheit werden sowohl die grundlegenden Konzepte relationaler Datenbankabfragen erlent. Weniger formal benannt werden wir uns um die Extraktion von Daten aus Datentabellen kümmern. Abfragen in GI Systemen können als der Kern jeder Analyse verstanden werden. 

## Lernziele 

Nach dieser Übung können Sie:

  *  beliebige thematische Abfragen auf Vektordatenattribute durchführen 
  *  räumliche Abfragen in Form von geometrischen und topologischen Abfragen unterscheiden und durchführen
  *  Abfragen verknüpfen


## Benötigte Materialien

* Daten:
  * [POI Marburg](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_points.zip)
  * [Open Streetmap Daten](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_nat.zip)
  * [Open Streetmap Daten](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_roads.zip)



## Aufgabe 03-01


In der Aufgabe 03-01 werden Attributwerte abgefragt.

* Wieviel Ampeln ("traffic_signals") gibt es in Marburg?
* Wieviele Objekte sind dem Typ "cafe" und "bar" in Marburg zugeordnet.
* Wieviele Objekte sind nicht vom Typ "university" ?
* Wieviele Objekte beinhalten das Wort Café in ihrem Namen? 
* Welche Objekte beinhalten zwar das Wort Café in ihrem Namen, sind aber nicht vom Typ "cafe" ?
* Suchen Sie alle Objekte die den exakten Namen "REWE" haben UND vom Typ "supermarket" sind.
* Suchen Sie alle Objekte die den exakten Namen "REWE" haben ODER vom Typ "supermarket" sind.
{: .notice--success}

## Hilfestellung 

Bitte beachten Sie in jedem Fall, dass die Suchbegriffe sowohl groß als auch klein, mit oder ohne Leerzeichen, nur Teilweise oder einmal mit und einmal ohne Umlaut eingetragen worden sind. Diese unterschiedlichen Eintragungen ein und derselben Kategorie sollten aber soweit als möglich bei den thematischen Abfragen berücksichtigt werden. 


## Aufgabe 03-02


In der Aufgabe 03-02 beschäftigen wir uns mit topologischen und geometrischen Abfragen.



  - Wieviele Punkte befinden sich in Naturgebieten?
  - Wieviele Punkte sind maximal 150m von Naturgebieten entfernt?
  - Wieviele restaurants oder bars sind max 150m von Naturgebieten entfernt?
  - Wieviele Straßen führen durch Naturgebiete?
  - Wie viele Punkte liegen im Umkreis von 500 m um den Marburger Bahnhof?
  - Wie viele bars liegen maximal 500 Meter von der nächsten Bushaltestelle?
  - Wie viele Punkte liegen im Umkreis von maximal 250 Metern um Parkplätze?
  - Von wievielen Punkte aus kann ein Arzt/Krankenhaus in weniger als 500 Meter Entfernung gefunden werden?
  - Wie viele Punkte der Kategorie Gastronomie liegen weiter als 1 km vom Bahnhof und gleichzeitig weniger als 1 km vom nächsten Briefkasten entfernt?
{: .notice--success}


#### Hinweise

 Seien Sie sich bewusst, dass Sie mehrere Abfragen hintereinander durchführen können. Hierzu müssen Sie das Abfrageergebnis ggf. als neuen Layer speichern (Rechtsklick auf das selektierte Layer, dann Auswahl, dann Layer aus selektierten Features erstellen). Bitte beachten Sie, dass die so erstellten Layer nur virtuell sind. Sie können Sie aber natürlich als Shape-Datensatz exportieren oder in Ihrer Geodatabase speichern.


