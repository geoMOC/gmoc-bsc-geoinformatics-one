---
title: Lerneinheit 1 - Warm Up QGIS
toc: true
header:
  image: /assets/images/splash_L01.png
  image_description: "The QGIS Evolution"
  caption: "The QGIS Evolution CC0 AG UI"
  

---
Der Einstieg in eine komplexe Software ist mühsam und verlangt einiges an Frusttoleranz. Durch Ähnlichkeit dere Werkzeuge und Konzepte bei ständiger Entwicklung ist es sinnvoll *Analog-Wissen* aufzubauen und sich den Zugang zu den Arbeitsabläufen *logisch-strukturiert* und **nicht** durch *auswendig lernen* der einzelnen Arbeitsschritte zu erarbeiten. Das ist nicht geschenkt zumal GIS Softwarepakete wie ArcGIS oder QGIS zu den eher komplexen Softwarearchitekturen gehören.
<!--more-->
## Was wir in dieser Einheit vor haben
Zur Mühsal des Erlernes sowohl neuer konzeptueller als auch Informationstechnik bezogener Problemfelder kommt auch noch die Auseinandersetzung mit einer neuen Software, die mit einer ungewohnten Graphical-User-Interface (GUI) aufwartet, hinzu. Um die Herausforderungen etwas zu verteilen fangen Sie Schritt für Schritt an und beginnen in dieser ersten Einheit mit einigen grundlegenden und typischen Aufgaben.  

## Lernziele 

Nach dieser Übung können Sie:
  *  QGIS installieren
  *  eine QGIS Projektdatei anlegen
  *  Datenformate und Datenmodelle unterscheiden
  *  Raster- und Vektordatensätze in QGIS öffnen
  *  Eigenschaften der Datenebenen kontrollieren
  *  Geometrien erzeugen (digitalisieren)


## Benötigte Materialien

### Daten
  * [Luftbild](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/marburg_RE.tif) von Marburg und Umgebung (Beispiel RGB-Bild als Rasterdatensatz)
  * [Wald Flächen](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_nat.zip) Ausschnitt aus dem aktuellen (11/2020) Open Streetmap (OSM) Datensatz
  * [Straßen](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_roads.zip) Ausschnitt aus dem aktuellen (11/2020) Open Streetmap (OSM) Datensatz
  * [Räumliche Objekte](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_objects.xls) Excel Tabelle.

### Software
  * [QGIS Installation](https://www.qgis.org/de/site/forusers/alldownloads.html). **Windows Nutzer** Installieren QGIS mit Hilfe des [osgeo4W](http://download.osgeo.org/osgeo4w/osgeo4w-setup-x86_64.exe) Installers. **Linux** Nutzer folgen den Anweisungen der [QGIS Installationsseite](https://www.qgis.org/de/site/forusers/alldownloads.html#linux). Weitere Informationen zur finden Sie unter  [hier](https://r-spatial.github.io/link2GI/articles/link2GI6.html).

### Einführende Materialien
  * [Eine sanfte Einführung in GIS](https://docs.qgis.org/3.10/de/docs/gentle_gis_introduction/index.html)
  * [QGIS Benutzerhandbuch 3.10 DE](https://docs.qgis.org/3.10/de/docs/user_manual/index.html) Die erste zentrale Referenz für Nutzer. Hier die aktuelle deutschsprachige Version. 
  * [QGIS Benutzerhandbuch 3.16 EN](https://docs.qgis.org/3.16/en/docs/user_manual/index.html) Die erste zentrale Referenz für Nutzer. Hier die aktuelle englischsprachige Version. 
  


## Aufgabe 01-01

Dieses Arbeitsblatt dient der Einführung in die verschiedenen Datenmodelle im GIS. Zudem lernen Sie, wie Sie eigene Raumdaten ins GIS importieren oder auch selbst im GIS erstellen können.

  * Erstellen Sie bitte ein Verzeichnis das **ohne** Sonderzeichen und Leerzeichen (im gesamten Pfad/Verzeichnisbaum) benannt ist
  * Legen Sie ein QGIS-Projekt an
  * Laden Sie die Datei `marburg_RE.tif` 
  * Informieren Sie sich über die Eigenschaften des Datensatzes. (Projektion, Datenmodell, Werte-Spektrum)
  * Laden Sie von der [geofabrik](http://download.geofabrik.de/) den Datensatz von Hessen herunter und entpacken das Archiv in einen Unterordner Ihres Projektverzeichnis das Sie `Daten` nennen.
  * Öffnen Sie nach dem Entpacken des Archivs die Datei `gis_osm_pois_free_1.shp` in Ihrem QGIS Projekt
  * Informieren Sie sich auch bei diesem Datensatz über die Eigenschaften. (Projektion, Datenmodell, Werte-Spektrum)
  * Schneiden Sie den Datensatz `gis_osm_pois_free_1` auf die Ausdehnung des Luftbildes `marburg_RE.tif` zu 
  * Exportieren Sie diese Punktdaten im *geopackage* Datenformat unter dem Namen `mr_points`
  * Importieren Sie die Tabelle `mr_objects.xls` (Datensatz [Räumliche Objekte](https://raw.githubusercontent.com/GeoMOER/moer-bsc-geoinfo-basic/master/docs/assets/data/mr_objects.xls)) als einen räumlichen Layer in ihr QGIS-Projekt
  * Erstellen Sie auf Grundlage des Luftbildes `marburg_RE.tif`:
      * Drei beliebige Flächen (Polygone), 
      * drei beliebige Straßen (Linienzüge) 
      * ergänzen Sie schließlich den Layer `mr_points` um 3 beliebige Positionen (Punkte) Ihrer Wahl
  * Geben Sie bei den neu erstellten Datensätzen als Koordinatensystem **WGS84** an. Tipp: Sie können zur besseren Orientierung auch eine Webkarte in Ihr Projekt laden (Weitere Informationen unter Hilfestellungen.
{: .notice--success}



## Aufgabe 01-02 

Leider können wir Sie nicht vollständig an dem Thema der korrekten Verortung von Geodatensätzen - also der adäquaten Projektion- vorbei manövrieren. Im Rahmen der Aufgabe 02-01 haben Sie Raster- und Vektordaten in QGIS importiert sowie eigene Vektordaten erstellt. Die räumliche Information der Daten lag jeweils in geographischen Koordinaten vor. Die von Ihnen benutzte Software QGIS führt immer eine Echtzeitprojektion durch mit dem Ziel diese Kugelkoordinaten auf den *flachen* Monitor zu projizieren. Dies hat jedoch nichts mit einer kartographischen Projektion zu tun. Nahezu alle räumlichen Analysen und geometrische Berechnungen funktionieren nur auf korrekt projizierten Daten.

Für den Beginn können wir Sie nur sehr nachdrücklich ermuntern das CRS (Coordinate Reference System) bzw KBS (Koordinatenbezugssystem) ihres *Projekts* und jeder Datenebene identisch zu halten. Für Deutschland ist das amtliche System [ETRS89 UTM 32 ](https://epsg.io/25832). Durch diese Sorgfalt kann eine Fehlpositionierung und so einer der häufigsten Alltagsfehler in der GIS Welt vermieden werden.
{: .notice--danger}

### Aufgabenstellung
* Erstellen Sie ein neues QGIS Projekt. Laden Sie als erstes die Rasterdatei `marburg_RE.tif` und dann im Anschluss die Vektordatensätze `mr_roads` und `mr_nat` ein.
   * Welche Projektionen besitzen die einzelnen Datensätze?
   * In welcher Projektion werden die Daten angezeigt? 
   * Wo können Sie die Projektion definieren, die zur Darstellung der Daten verwendet werden soll?
   * Was versteht man unter einer *on the fly* bzw. *Echtzeit* Projizierung?
* Weisen Sie dem Layer `mr_nat` das geographische Referenzsystem `WGS 84` zu. 
* Projizieren Sie anschließend alle Datensätze in *ETRS89 UTM 32* 
   * Warum konnten Sie dem Layer `mr_nat` die Projektion *ETRS89 UTM 32* nicht direkt zuweisen
{: .notice--success}

## Hilfestellungen

Als konkreten Einstieg für die Bearbeitung von Aufgabe 1 möchten wir Ihnen noch einige Einstiegshilfen für QGIS anbieten. QGIS ist ein komplexes Softwareprodukt, das nicht nur in  unterschiedlichen Versionen auf allen gängigen OS-Plattformen verfügbar ist, sondern zusätzlich vollständig individuell anpassbar ist. Daher kursieren im Netz aus den vergangenen 15 Jahren eine Vielzahl von Hilfen, Handbüchern und Tutorials - nicht jeder Treffer ist geeignet und erst recht nicht jedes Tutorial passt auf Ihre Version.

Einen ersten Anlaufpunkt für konkrete Informationen stellt die integrierte Hilfe des Softwarepakets dar. Darüber hinaus ist eine umfangreiche Dokumentation verfügbar. Die jeweils aktuelle [QGIS Landing Page](https://www.qgis.org/de/site/forusers/index.html) ist der zentrale Zugang zu allen offiziell vom Projekt verfügbar gemachten Dokumentationen. Bei allen Seiten gilt achten Sie darauf die Hilfe zu Ihrer passenden QGIS Version anzuschauen. Falls diese (noch) nicht verfügbar ist versuchenen Sie es mit der jeweils nächsten Vorgängerversion. **Achtung** der Übergang von QGIS2.x auf QGIS3.x markiert erhebliche Veränderungen. In der Regel sind Anleitungen für QGIS  2.x unbrauchbar. 


### Einrichtung eines QGIS-Projekts 

Wir raten Ihnen **dringend** bei Rechnern mit einem Heimatverzeichnis in der Cloud/im Netz (z.B. in der Uni-Pools) die Daten auf einer lokalen Festplatte abzuspeichern.  Hierfür müssen Sie zunächst eine Ordnerstruktur für Ihr Projekt anlegen. Bitte achten Sie darauf **keine** Sonderzeichen, Umlaute oder Leerzeichen zu verwenden. Hilfe zur Projektdatei finden Sie unter [Arbeiten mit Projektdateien](https://docs.qgis.org/3.10/de/docs/user_manual/introduction/project_files.html).

### Digitalisieren von Geometriedaten

Die manuelle Erzeugung von Vektordaten wird allgemein als *digitalisieren* bezeichnet. Dabei erzeugen Sie auf z.B. Grundlage von Rasterbilddateien wie Satellitenbildszenen, Luftbildern, thematischen und topographischen Karten, einfachen Screenshots oder anderen Vorlagen Ihre eigenen vektorbasierten Datensätze. Schauen Sie sich dazu die QGIS Hilfe zur  [Digitalisierung](https://docs.qgis.org/3.10/de/docs/user_manual/working_with_vector/editing_geometry_attributes.html) an. Ein ausführliches Anwendungsbeispiel finden Sie unter [Digitizing Forest Stands](https://docs.qgis.org/3.10/en/docs/training_manual/forestry/stands_digitazing.html)

### Zuschneiden von Vektordaten 
Diese Aufgabe ist ein gutes Beispiel wie knifflig die Suche nach Hilfe sein kann. Natürlich gilt immer dass Sie das Internet durchsuchen können. Versuchen Sie es zum Beispiel mit "*zuschneiden von vektordaten qgis*". Sie haben viele Treffer aber bei genauer Betrachtung finden Sie nichts über das Zuschneiden von Vektordaten mit Hilfe einer Raster-Datei. Was geschieht beim Zuschneiden? Sie müssen offensichtlich einem Werkzeug mitteilen was die gewünschte Ausdehnung ist. Fangen Sie mit diesem Wissen nochmal an. Nur diesmal nutzen Sie die Werkzeug-Leiste und tippen dort "*zuschneiden*" bzw. "*clip*" ein. Es werden einige Treffer angezeigt. Unter anderem auch *Vektor auf Ausdehnung zuschneiden*. Wenn Sie diesen auswählen können Sie bei der *Ausdehnung* drei Optionen wählen...

###  Tabellen in QGIS importieren
Der Import von Tabellen beinhaltet eine Vielzahl von Fallstricken. Ganz generell nutzen Tabellendaten in QGIS nur dann etwas wenn sie entweder selbst Koordinaten (also geographische Informationen) enthalten oder aber einen Schlüssel wie z.B eine ID die bereits existierenden Geometriedaten zuzuordnen ist. Generell können sie aber folgendem Schema folgen:
[Import von Tabellenblättern oder CSV-Dateien](http://www.qgistutorials.com/de/docs/3/importing_spreadsheets_csv.html)

### Arbeiten mit Projektionen
Das Kapitel 
[Arbeiten mit Projektionen](https://docs.qgis.org/3.10/de/docs/user_manual/working_with_projections/working_with_projections.html) ist für Anfängerinnen schwer verständlich. Wichtig ist hier vor allem das korrekte Zuweisen von Projektionen. Für das Umprojizieren von Vektordaten lohnt sich ein Blick in [Reprojecting and Transforming Data](https://docs.qgis.org/3.10/de/docs/training_manual/vector_analysis/reproject_transform.html).