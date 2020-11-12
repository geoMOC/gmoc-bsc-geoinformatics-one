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

* Daten:
  * [SRTM Geländemodell](http://srtm.csi.cgiar.org/SELECTION/inputCoord.asp)



## Aufgabe 04-01


*   Laden Sie sich unter der obigen Adresse die passende Kachel (Ausschnitt) des SRTM Geländemodell von Marburg herunter. 
*   Was zeigt Ihnen der Datensatz?
*   Projizieren Sie das Geländemodell in ETRS89 UTM32 und schneiden es auf den Marburg Ausschnitt zu.
*   Berechnen Sie auf der Grundlage des Geländemodells von wo aus die E-Kirche sichtbar ist.
*   Berechnen Sie die Hangneigung, Exposition und Abflussrichtung. 
*   Extrahieren Sie für den Marktplatz (Brunnen) diese Werte.
*   Wenden Sie einen 5*5 Mittelwertsfilter auf die Geländehöhe an. Beschreiben Sie das Resultat in ein bis zwei Sätzen. 
*   Berechnen Sie, die minimale, maximale und mittlere Hangneigung in städtischem Gebiet (Verwaltungsgrenze). 
{: .notice--success}

## Hilfestellung 

*  Verwenden Sie zum Ausschneiden des Rasters einen der Marburg-Layer aus den vorherigen Sitzungen als Vorlage.
*  Das Stichwort für die QGIS Hilfe zum Mittelwertsfilter ist "neighbors" in der Verarbeitungsbox. Als Resultat wird r.neighbors aus der GRASS GIS Funktionssammlung angezeigt
*  Zur Sichtbarkeitsanalyse können sie das Plugin "Visibility Analysys" installieren. Es wird im Anschluß unter den Verarbeitungswerkzeugen angezeigt.
*  Verwenden Sie zonale Statistiken um sich die min/max/mittel Werte als Tabelle auszugeben 

