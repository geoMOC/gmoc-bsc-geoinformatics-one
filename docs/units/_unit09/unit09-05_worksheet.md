---
title: Lerneinheit 5 - Kosten und Kriterien
toc: true
header:
  image: /assets/images/01-splash.jpg
  image_description: "John Snows "
  caption: "Map: [**Dr. John Snow**](https://de.wikipedia.org/wiki/John_Snow_(Mediziner)) [Wellcome Library via wikimedia](https://w.wiki/QtV)"

---


In dieser Aufgabe sollen Sie unterschiedliche Analysen auf der Grundlage vorgegebener Kriterien  durchführen. Letztendlich suchen Sie nach *Eignung* oder *Nichteignung* oder auch nach *Widerständen* oder *Kosten*, welche die Eignung oder Nutzung eines Pixels (Rasterelements) determinieren.


<!--more-->

Betrachtet man dies auf eine Bewegung im Raum so sind es diese Kosten die das Überwinden einer Distanz, leicht oder beschwerlich, billig oder teuer, attraktiv oder unattraktiv usw. machen. Vor diesem Hintergrund müssen die einfließenden Kriterien für die Planung Ihrer Strecke in Bezug auf die Zielsetzung bewertend gewichtet werden. 


  


## Was wir in dieser Einheit vor haben

Im Rahmen der Übung werden Sie eine typische Eignungsanalyse und im Anschluss eine Kostenpfadanalyse durchführen. Dazu gehört die Vorbereitung des Kostenrasters und die Durchführungen und Interpretation der Analyse.


## Lernziele 

Nach dieser Übung können Sie:

  *  Vektordaten rastern
  *  Rasterdaten verrechnen
  *  Eine Multikritereien-Evaluation durchführen und diese Grundlagen 
  *  für eine Kostenpfadanalyse nutzen



## Aufgabe 05-01

## Benötigte Materialien

*  MOF-Geländemodell 1 Meter Auflösung
*  Corine Landnutzung MOF

Die Daten finden Sie in der Archiv-Datei [praxis_L05.zip]((https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/praxis_L05.zip))

Bitte entpacken Sie diese in einen geeigneten Ordner. 


Sie sollen exemplarisch die Entscheidungsfindung  – Mehrere Ziele, mehrere Kriterien vorbereiten. Wie Sie sich erinnern geht es um die konkurrierende Nutzung des Uniwalds als Wildkatzenhabitat bzw. als Freizeitgelände. 

*  Laden Sie die Daten herunter und prüfen Sie diese in gewohnter Weise
*  Berechnen Sie die Hangneigung 
*  Reklassifizieren Sie die [Corine Landnutzungsdaten](https://land.copernicus.eu/pan-european/corine-land-cover/clc2018?tab=mapview) (Sie finden die bereits vorbereitete Datei im Archiv unter `clc2018_1m_MOF_25832.tif`) in *Wald*, *Kein Wald*
*  Zur Vorbereitung der Multikriterien-Evaluation müssen die Raster in ganzzahlige Klassen reklassifiziert werden. Also z.B. die Hangneigung in drei Klassen 0-15, 15-30 >30 Grad.
* Legen Sie für jedes Layer eine Gewichtung fest. 
* Legen Sie für jede Klasse in diesem Layer eine Bewertung von 0-10 fest. Bedenken Sie bitte dass die Festlegung der Bewertung in Bezug auf die Fragestellung gewählt werden muss. 
*  Diskutieren Sie die Ergebnisse (2 Sätze)
{: .notice--success}

## Hilfestellung 

*  Sie können für die MCE z.B. das Plugin `WMCA Weighted Multicriteria Analysis`nutzen. Es wird nach der Installation unter dem Menü `Raster` angezeigt.
* Weitere und deutlich tiefergehende Hilfe finden Sie unter [Multi Criteria Overlay Analysis (QGIS3)](https://www.qgistutorials.com/en/docs/3/multi_criteria_overlay.html). Da es sich um eine zentrale GIS-Funktionalität handelt werden Sie unter allen GRIS Systemen ähnliche Konzepte finden die sie entweder direkt nutzen oder analog auf QGIS übertragen können z.B. das [MCE Tutorial für SAGA GIS](https://svwh.dl.sourceforge.net/project/saga-gis/SAGA%20-%20Documentation/Tutorials/Multi_Criteria_Evaluation_Tutorial/MultiTutorial2.pdf).


 

## Aufgabe 05-02

## Benötigte Materialien

*  MOF-Geländemodell 1 Meter Auflösung
*  OSM Wege MOF
*  Corine Landnutzung MOF
*  Koordinaten Strecken-Anfang (478188,5632178), Strecken-Ende(476170,5631657) beide [EPSG:32632]

Die Daten finden Sie in der Archiv-Datei [praxis_L05.zip]((https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/praxis_L05.zip))

Bitte entpacken Sie diese in einen geeigneten Ordner.
Sie sollen einen Fitness-Trail durch den Uniwald (Marburg Open Forest, MOF) bei Caldern planen. Diese soll vom Parkplatz in der Nähe des Kreisverkehrs am südöstlichen Rand bis zum Grillplatz am nordwestlichen Ende verlaufen. Sie haben die Vorstellung, dass die Strecke bevorzugt durch Wald und möglichst weit weg von Wegen entlang führen soll. Außerdem soll Ihre Strecke (um möglichst anspruchsvoll zu sein) maximale Steigungen aufweisen.

*  Laden Sie die Daten herunter und prüfen Sie diese in gewohnter Weise
*  Machen Sie sich mit dem Konzept der Kostenanalyse vertraut
*  Berechnen Sie die Hangneigung 
*  Reklassifizieren Sie die [Corine Landnutzungsdaten](https://land.copernicus.eu/pan-european/corine-land-cover/clc2018?tab=mapview) (Sie finden die bereits vorbereitete Datei im Archiv unter `clc2018_1m_MOF_25832.tif`) in *Wald*, *Kein Wald*
*  Berechnen Sie die Entfernung von den Wegen (`OSM_roads_MOF_25832.gpkg`) als Raster
*  Legen Sie für jeden Rasterwert einen Wertebereich fest, der die *Kosten* zur Überwindung der Zelle beinhaltet. Sinnvollerweise sind eher unattraktive Räume mit hohen Werten und attraktive Räume mit niedrigen Werten belegt werden. Die Werte für die Hangneigung und für die Entfernung von der Straße sollten kontinuierlich bleiben und nicht in Klassen eingeteilt werden. 
*  Normalisieren (Skalieren) Sie die Rasterwerte, indem Sie das Raster durch den jeweiligen maximalen Wert teilen.
* Verrechnen Sie die Raster nun zu einem Gesamtkostenraster. Überlegen Sie sich dabei ob allen drei Kriterien gleichgewichtet behandeln wollen, oder ob Sie z.B. der Hangneigung eine höhere Bedeutung zuweisen wollen.
*  Berechnen Sie auf dieser Grundlage den attraktivsten (="kostengünstigsten") Weg zwischen dem Start und Zielpunkt.
*  Diskutieren Sie die Ergebnisse (2 Sätze)
{: .notice--success}

## Hilfestellung 

* Reklassifizieren Sie die Raster Daten der Landnutzung z.B. mit dem Werkzeug `Nach Tabelle neuklassifizieren`. Sie können verschiedene Werkzeuge zu diesem häufig benötigten Funktion nutzen. für einen Überblick geben Sie `klassifizieren` in der Werkzeugleiste ein. 
* Die Normalisierung von Raster Daten kann einfach mit dem SAGA Modul `Grid Normalisation` durchgeführt werden. alternativ können Sie diese mit dem [Raster-Rechner](https://docs.qgis.org/3.10/de/docs/user_manual/working_with_raster/raster_analysis.html#raster-calculator) nach der Formel `xnorm = (x-min(x))/(max(x)-min(x))` berechnen. Der Raster Rechner ist als Raster Taschenrechner für zahlreiche Operationen ein extrem wichtiges Werkzeug. 
* Die Gewichtung kann dann durch eine einfache Multiplikation (`Raster-Rechner`) des jeweiligen Raster mit dem Gewichtungswert erreicht werden. Z.B. Gleichgewichtung `Raster1*Raster2*Raster3/3` Gewichtung Raster1 Faktor 0.5 Raster2 und Raster3 Faktor 0.25 `0.5*Raster1 + 0.25* Raster2 + 0.25*Raster3`
*  Zur Least Cost Path Analyse können sie das Plugin "Least Cost Path" installieren. Es
wird im Anschluss unter den Verarbeitungswerkzeugen angezeigt.