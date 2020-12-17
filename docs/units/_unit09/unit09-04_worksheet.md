---
title: Lerneinheit 5 - Kosten und Kriterien
toc: true
header:
  image: /assets/images/01-splash.jpg
  image_description: "John Snows "
  caption: "Map: [**Dr. John Snow**](https://de.wikipedia.org/wiki/John_Snow_(Mediziner)) [Wellcome Library via wikimedia](https://w.wiki/QtV)"

---


In dieser Aufgabe sollen Sie unterschiedliche Analysen auf der Grundlage vorgegebener Kriterien  durchführen. Letztendlich suchen Sie nach der  *Eignung* oder *Nichteignung* oder berechnen räumliche  *Widerstände* oder *Kosten*, welche einen Schätzwert für die Eignung oder Nutzung eines Pixels (Rasterelements) bestimmen.


<!--more-->

Betrachtet man dies auf eine Bewegung im Raum so sind können die Werte in einem Pixel als Kosten die das Überwinden einer Distanz, leicht oder beschwerlich, billig oder teuer, attraktiv oder unattraktiv usw. machen gelten. Vor diesem Hintergrund müssen die einfließenden Kriterien für die Planung einer z.B. "kostengünstigen Strecke" in Bezug auf die Zielsetzung bewertet und evtl. gewichtet werden. 


  


## Was wir in dieser Einheit vor haben

Im Rahmen der Übung werden Sie eine Eignungsanalyse und im Anschluss eine Kostenpfadanalyse durchführen. Dazu gehört natürlich Datenvorbereitung was gerade bei einem Kostenraster sehr aufwendig sein kann aber auch die Interpretation der Analysen ist in der Regel aufwendig.


## Lernziele 

Nach dieser Übung können Sie:

  *  unterschiedlichste Datenebenen zielorientiert zu bearbeiten und kombinieren
  *  die Bedeutung verschiedener Kriterien identfizieren und einschätzen
  *  durch Verrechnen geeigneter Datenebenen eine Eignungsanalyse durchführen
  *  eine Kostenanalyse planen und durchführen



## Aufgabe 05-01

## Benötigte Materialien

*  MOF-Geländemodell 1 Meter Auflösung
*  Corine Landnutzung MOF
* Die Daten finden Sie im  Zip-Archiv  [praxis_L05.zip](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/praxis_L05.zip)

Sie sollen eine Entscheidungsfindung auf der Grundlage mehrere Kriterien vorbereiten. Sie sollen die Eignung des Uniwalds als Wildkatzenhabitat untersuchen. 

*  Laden Sie die Daten herunter (prüfen Sie diese in gewohnter Weise)
*  Berechnen Sie die Hangneigung 
*  Extrahieren Sie die aus den  [Corine Landnutzungsdaten](https://land.copernicus.eu/pan-european/corine-land-cover/clc2018?tab=mapview) alle Waldflächen so daß Sie ein Raster mit den Werten 1 für *Waldflächen* und 0 für *Keine Waldflächen*. (Sie finden bereits zugeschnittene Corine-Daten im heruntergeladenen Archiv unter dem Dateinamen `clc2018_1m_MOF_25832.tif`) 
*  Zur Vorbereitung der Multikriterien-Evaluation müssen die Rasterwerte in *ganzzahlige* Werte überführt (reklassifiziert) werden. Also z.B. die Hangneigung in drei Klassen 0-15 Grad = Klasse mit dem Wert 1, 15-30 Grad = Klasse mit Wert 2 und  > 30 Grad = Klasse mit Wert 3.
* Legen Sie für jede Datenebene eine Gewichtung gemäß der von Ihnen festgelegten Bedeutung in Relation zu ihrer Eignung fest (z.B. Wald/Nichtwald = Faktor 5, Hangneigung = Faktor 3 etc..)
* Legen Sie für jede Klasse in diesem Layer eine Bewertung von 0-10 fest (z.B. Wald = 10, Nichtwald = 1, Hangneigung Klasse 1 = 5 etc., bedenken Sie bitte dass die Festlegung der Bewertung zwingend die hinsichtlich Fragestellung fachlich zu bewertenende Bedeutung der Kriterien für die Fragestellung berücksichtigen muß.) 
* Fassen Sie die Ergebnisse  in max. 2 Sätzen zusammen.
{: .notice--success}

## Hilfestellung 

*  Sie können für die rasterbasierte Umrechnung (Klassifikation/Reklassifikation) der Werte  als generrelles Werkzeug den *Rasterrechner*  oder auch spezielle Werkezeuge wie z.B. das Plugin `WMCA Weighted Multicriteria Analysis` nutzen. Dieses Plugin wird nach der Installation unter dem Haupt-Menü `Raster` angezeigt. Sie müssen evtl. *"Auch experimentelle Erweiterungen anzeigen"* unter den Einstellungen aktivieren.
* Weitere und deutlich tiefergehende Hilfe für den gesamten Arbeitsablauf finden Sie QGIS-spezifisch unter [Multi Criteria Overlay Analysis (QGIS3)](https://www.qgistutorials.com/en/docs/3/multi_criteria_overlay.html). 

Da es sich um eine zentrale Raster-GIS-Funktionalität handelt werden Sie unter allen GI Softwarepaketen ähnliche Werkzeug-Konzepte finden. Die verfügbaren Tutorials und Anleitungen können Si über die Verarbeitungswerkezuge entweder direkt nutzen oder analog auf QGIS übertragen [z.B. das MCE Tutorial für SAGA GIS](https://svwh.dl.sourceforge.net/project/saga-gis/SAGA%20-%20Documentation/Tutorials/Multi_Criteria_Evaluation_Tutorial/MultiTutorial2.pdf).



## Aufgabe 05-02

## Benötigte Materialien

*  MOF-Geländemodell 1 Meter Auflösung
*  OSM Wege MOF
*  Corine Landnutzung MOF
*  Koordinaten (ETRS89, UTM32 EPSG:32632) Position *Kreisel*  (478188,5632178), Position Grillhütte (476170,5631657)
*  [Daten-Archiv]((https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/praxis_L05.zip))

## Aufgabenstellung 
Sie sollen einen Cross-Crountry Fitness-Trail durch den Uniwald (Marburg Open Forest, MOF) bei Caldern planen. Der Trail beginnt am Parkplatz in der Nähe des Kreisverkehrs am südöstlichen Rand und endet am Grillplatz am nordwestlichen Ende verlaufen. Die Vorgaben sind: 
* die Strecke soll bevorzugt durch Wald führen
* die Strecke soll möglichst weit von Wegen entfernt sein. 
* die Strecke soll maximale Steigungen bevorzugen (hoher Trainingseffekt).

## Vorgehensweise 
*  Machen Sie sich mit dem Konzept der Kostenanalyse vertraut
*  Herunterladen und überprüfen der Daten
*  Berechnen Sie die Hangneigung 
*  Nutzen Sie reklassifizierten Corine Daten (*Wald*, *Kein Wald*).
*  Berechnen Sie ein Entfernungsraster das den Abstsnd zu den Wegen (`OSM_roads_MOF_25832.gpkg`) beinhaltet (räumliche Auflösung wie das Hangneigungsraster).
*  Legen Sie für jede Rasterklasse (z.B. Wald Nicht-Wald) Werte fest, die die *Kosten* bzw den *Reibungswert* zur Überwindung/Nutzung der Zelle abbildet. Sinnvoll ist es also unattraktive Zellen mit hohen Werten und attraktive Zellen mit niedrigen Werten zu belegen. Die Werte für die Hangneigung und für die Entfernung von der Straße sollten kontinuierlich bleiben und nicht in Klassen eingeteilt werden. 
* Normalisieren (Skalieren) Sie die Rasterwerte
* Verrechnen Sie die einzelnen Raster nun zu einem Gesamtkostenraster. Überlegen Sie sich dabei ob allen drei Kriterien gleichgewichtet eingehen sollen, oder ob Sie z.B. der Hangneigung eine höhere Bedeutung zuweisen wollen.
* Berechnen Sie auf dieser Grundlage den attraktivsten (="kostengünstigsten") Weg zwischen dem Start und Zielpunkt.
* Bewschreiben Sie das Ergebnis (2 Sätze)
{: .notice--success}

## Hilfestellung 

* Reklassifizieren Sie die Raster Daten der Landnutzung z.B. mit dem Werkzeug `Nach Tabelle neuklassifizieren`. Sie können verschiedene Werkzeuge zu diesem häufig benötigten Funktion nutzen. für einen Überblick geben Sie `klassifizieren` in der Werkzeugleiste ein. 
* Die Normalisierung von Raster Daten kann einfach mit dem SAGA Modul `Grid Normalisation` durchgeführt werden. alternativ können Sie diese mit dem [Raster-Rechner](https://docs.qgis.org/3.10/de/docs/user_manual/working_with_raster/raster_analysis.html#raster-calculator) nach der Formel `xnorm = (x-min(x))/(max(x)-min(x))` berechnen. Der Raster Rechner ist als Raster Taschenrechner für zahlreiche Operationen ein extrem wichtiges Werkzeug. 
* Die Gewichtung kann dann durch eine einfache Multiplikation (`Raster-Rechner`) des jeweiligen Raster mit dem Gewichtungswert erreicht werden. Z.B. Gleichgewichtung `Raster1*Raster2*Raster3/3` Gewichtung Raster1 Faktor 0.5 Raster2 und Raster3 Faktor 0.25 `0.5*Raster1 + 0.25* Raster2 + 0.25*Raster3`
*  Zur Least Cost Path Analyse können sie das Plugin "Least Cost Path" installieren. Es
wird im Anschluss unter den Verarbeitungswerkzeugen angezeigt.