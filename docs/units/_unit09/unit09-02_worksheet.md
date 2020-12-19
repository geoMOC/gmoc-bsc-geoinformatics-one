---
title: Lerneinheit 3 - Fragen & Antworten
toc: true
header:
  image: /assets/images/01-splash.jpg
  image_description: "John Snows "
  caption: "Map: [**Dr. John Snow**](https://de.wikipedia.org/wiki/John_Snow_(Mediziner)) [Wellcome Library via wikimedia](https://w.wiki/QtV)"

---


Das systematische Abfragen von Datenbankinhalten sind Sie aus dem Alltag gewöhnt. Sei es die Abfrage von Zugverbindungen, Kinokarten die Sie online bestellen  oder die Suchanfrage bei Google. <!--more-->
Auch die Integration räumlicher Attribute in Abfragen ist Alltag für Sie. Falls sie zb. die *Location based Services* in Google aktiviert haben werden Sie regelmäßig mit lokalisierter Werbung oder Abstimmungsanfragen bedacht. Doch wie können sie solche Abfragen selber gestalten und was ist die grundsätzliche Wirkungsweise?

## Was wir in dieser Einheit vor haben
In dieser Lerneinheit werden grundlegende Konzepte von Datenbankabfragen erlernt. Weniger formal werden Sie sich um die Extraktion von Daten aus Datentabellen kümmern. Abfragen in GI Systemen können sind ein wesentliches Standbein der meisten Analysen. 

## Lernziele 

Nach dieser Übung können Sie:

  *  beliebige thematische und räumliche Abfragen auf Vektordatenattribute durchführen 
  *  geometrische und topologische Abfragen unterscheiden
  *  Abfragen verknüpfen


## Benötigte Materialien

### Daten
  * [Points of Interest (POI) Marburg](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_points.zip). Sie können diese Datei verwenden oder die von Ihnen in Aufgabe 1 erzeugte Datei benutzen. 
  * [Wald Flächen](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_nat.zip) Ausschnitt aus dem aktuellen (11/2020) Open Streetmap (OSM) Datensatz
  * [Straßen](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_roads.zip) Ausschnitt aus dem aktuellen (11/2020) Open Streetmap (OSM) Datensatz



## Aufgabe 02-01


In der Aufgabe 02-01 werden Attributwerte abgefragt.

* Wieviel Ampeln ("traffic_signals") gibt es in Marburg?
* Wieviele Objekte weisen die Merkmalsausprägung "cafe" und "bar" auf.
* Wieviele Objekte sind weisen **nicht** die Merkmalsausprägung "university" auf?
* Wieviele Objekte beinhalten das Wort Café in ihrem Namen (Attribut name) ? 
* Welche Objekte beinhalten zwar das Wort Café in ihrem Namen, aber nicht der die Merkmalsausprägung "cafe" des Attributs flcass?
* Suchen Sie alle Objekte die den exakten Namen "REWE" haben **und** vom Typ "supermarket" sind.
* Suchen Sie alle Objekte die den exakten Namen "REWE" haben **oder** vom Typ "supermarket" sind.
{: .notice--success}

## Hilfestellung 

Bitte beachten Sie in jedem Fall, dass die Suchbegriffe sowohl groß als auch klein, mit oder ohne Leerzeichen, nur Teilweise oder einmal mit und einmal ohne Umlaut eingetragen worden sind. Diese unterschiedlichen Eintragungen ein und derselben Kategorie sollten aber soweit als möglich bei den thematischen Abfragen berücksichtigt werden. 


## Aufgabe 02-02


In der Aufgabe 02-02 beschäftigen wir uns mit topologischen und geometrischen Abfragen.

  - Wieviele Punkte (des POI-Datensatzes) befinden sich in Waldflächen (mr_nat)?
  - Wieviele Punkte (des POI-Datensatzes) sind maximal 150 Meter von Waldflächen entfernt?
  - Wieviele "restaurants" oder "bars"" sind max 150 Meter von Waldflächen entfernt?
  - Wieviele Straßen führen durch Waldflächen?
  - Wie viele Punkte (des POI-Datensatzes) liegen im Umkreis von 500 Metern um den Marburger Bahnhof?
  - Wie viele Bars sind maximal 500 Meter von der nächsten Bushaltestelle entfernt?
  - Wie viele Punkte (des POI-Datensatzes) liegen im Umkreis von maximal 250 Metern um Parkplätze?
  - Von wievielen Punkte (des POI-Datensatzes) aus kann ein Arzt/Krankenhaus in weniger als 500 Meter Entfernung gefunden werden?
  - Wie viele Punkte der Kategorie Gastronomie liegen weiter als 1 Kilometer vom Bahnhof und gleichzeitig weniger als 1 Kilometer vom nächsten Briefkasten entfernt?
{: .notice--success}


#### Hinweise

 Sie können mehrere Abfragen hintereinander durchführen. Hierzu müssen Sie das Abfrageergebnis ggf. als neuen Layer speichern (Rechtsklick auf das selektierte Layer, dann Auswahl, dann Layer aus selektierten Features erstellen). Bitte beachten Sie, dass die so erstellten Layer nur virtuell sind. Sie können Sie aber natürlich als Geopackage-Datensatz exportieren.

