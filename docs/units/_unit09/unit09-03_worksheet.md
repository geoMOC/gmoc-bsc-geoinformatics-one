---
title: Lerneinheit 4 - Analysen
toc: true
header:
  image: /assets/images/01-splash.jpg
  image_description: "John Snows "
  caption: "Map: [**Dr. John Snow**](https://de.wikipedia.org/wiki/John_Snow_(Mediziner)) [Wellcome Library via wikimedia](https://w.wiki/QtV)"

---


Digitale Geländemodelle liegen in der Regel als Rasterdaten vor und werden häufig in GIS-Analysen verwendet. Dabei tragen diese sowohl unmittelbar zur Höheninformation als auch mittelbar als z. B. morphometrische oder hydrologische Basisdatensätze zum prosessorientierten Erkenntnisgewinn bei.

<!--more-->

Der Themenkomplex der digitalen Geländemodelle inkl. deren Erstellung auf Grundlage unterschiedlicher Fernerkundungssensoren ist vielfältig. Die Materialien im Reader skizzieren verschiedene häufig verwendete Ableitungen und räumliche Filter. Diese Konzepte können auf nahezu alle Rasterdaten angewendet werden.


## Was wir in dieser Einheit vor haben

Im Rahmen der Übung werden Sie Informationen aus digitalen Geländemodellen ableiten und sich mit räumlichen Filtermethoden näher beschäftigen.


## Lernziele 

Nach dieser Übung können Sie:

  *  Neue Rasterdaten durch Anwendung typischer Werkzeuge (Algorithmen) erzeugen
  *  Diese abgeleiteten Informationen in Fragestellungen zielgerichtet einsetzen
  *  Abfagen auf solchen Rasterdaten durchführen.


## Benötigte Materialien

### Daten
  * [SRTM Geländemodell CGIAR](https://bigdata.cgiar.org/srtm-90m-digital-elevation-database/)
  * [SRTM Kachel in Ilias](https://ilias.uni-marburg.de/ilias.php?ref_id=2225588&cmd=return&cmdClass=ilrepositorygui&cmdNode=wi&baseClass=ilRepositoryGUI&redirectSource=ilobjfilegui&cmdMode=)


## Aufgabe 04-01


*   Laden Sie sich unter der obigen Adresse die passende Kachel (Ausschnitt) des SRTM Geländemodells von Marburg herunter. 
*   Was zeigt Ihnen der Datensatz?
*   Projizieren Sie das Geländemodell in ETRS89 UTM32 und schneiden es auf den Marburg Ausschnitt zu.
*   Berechnen Sie die Hangneigung, Exposition und Abflussrichtung. 
*   Extrahieren Sie für den Marktplatz (Position Brunnen) obige Werte.
*   Wenden Sie einen 5*5 Mittelwertsfilter auf die Geländehöhe an. Beschreiben Sie das Resultat in jeweils einem Satz. 
*   Berechnen Sie, die minimale, maximale und mittlere Hangneigung in städtischem Gebiet (Ausdehnung Luftbild). 
{: .notice--success}

## Hilfestellung 

*  Verwenden Sie zum Ausschneiden des Rasters einen der Marburg-Layer aus den vorherigen Sitzungen als Vorlage.
*  Das Stichwort für die QGIS Hilfe zum Mittelwertsfilter ist "neighbors"  oder auch (filter) in der Verarbeitungsbox. Als Resultat wird z.B. r.neighbors aus der GRASS GIS Funktionssammlung angezeigt. bei "filter" gibt es eine Reihe von Treffern. Hier ist ein guter Einstieg "Simple Filter" aus der Funktionssammlung von SAGA GIS.
*  Verwenden Sie zonale Statistiken um sich die min/max/mittel Werte eines definierten Gebiets als Tabelle auszugeben. Für Marburg können Sie entweder ein Stadtgebiet nach ihrere Einschätzung als Polygon abdigitalisieren oder z.B. auf die Suche nach Verwaltungsgrenzen gehen. Hier wäre z.b. die [Bundesamt für Kartographie und Geodäsie Open Data Server](https://gdz.bkg.bund.de/index.php/default/open-data.html) eine gute Startmöglichkeit.

x