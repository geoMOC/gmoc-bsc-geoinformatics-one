---
title: Digitale Geländemodelle  – Von der Höhe zur komplexen Information
toc: true
toc_label: Inhalt


---


Digitale Geländemodelle sind eine weithin genutzte Datenquelle für die räumliche Analyse. Im Original enthalten Sie in einem Rasterdatenmodell die Information der Höhe einer Rasterzelle. Aus dieser   Information können zahlreiche abgeleitete Informationen erzeugt werden. Diese Einheit ist exemplarisch   als leicht nachvollziehbares Beispiel für das Vorgehen bei Ableitung von Informationen aus raum kontinuierlichen Datensätzen gedacht. Neben der reinen Ableitung werden daher zudem mögliche funktionale Ableitungskonzepte wie potentielle Massentransporte, Feuchtigkeitsindizes angesprochen.


## Geomorphometrie oder wie aus einfachen Ableitungen wertvolle Informationen entstehen


Die Geomorphometrie beschäftigt sich mit der quantitativen Beschreibung und Analyse der Erdoberfläche. Zu diesem Zweck werden aus digitalen Geländemodellen (DGM) verschiedene Geländeparameter abgeleitet. Neigung, Exposition und Kurvatur (Krümmung) des Geländes gehören zu den Informationen, die am häufigsten aus Geländemodellen extrahiert und in verschiedensten Anwendungen eingesetzt werden. Als Beispiele seien die Verwendung der Exposition in vegetationsgeographischen Fragestellungen, die Modellierung von potentiellem alpinem Permafrost (Höhe, Zürich, Schweiz Exposition und Neigung) oder die Modellierung von Lawinengefahren (Neigung, Exposition) genannt.

### Beispiele impliziter Information

Ein digitales Geländemodell enthält neben der reinen Höhe der Raumkoordinaten (oder Raumflächen) eine Reihe weiterer, impliziter Information. “Implizite Information” heißt, dass zusätzliche Informationen aus der lagebezogenen Höheninformation eines Geländemodells abgeleitet werden können, ohne explizit gespeichert zu sein. Zur Ableitung solcher impliziter Information sind in der Regel geeignete mathematische Methoden notwendig. Dieser Zusammenhang von impliziter und expliziter Information lässt sich analog auf eine Vielzahl von Datensätzen und Geoobjekten übertragen. Die nachfolgenden Abbildungen zeigen ein Geländemodell des Türlersees (bei Zürich in der Schweiz) und durch Ableitung erzeugte Information aus diesen Daten.


### Primärdatensatz Höhe

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ExtracTopoOb-DGM.png" alt="Digitales Geländemodell vom Gebiet Türlersee als geschummerte Höhenschichtdarstellung (Hugentobler 2000)" caption="*Digitales Geländemodell vom Gebiet Türlersee als geschummerte Höhenschichtdarstellung (Hugentobler 2000)*" %}


### Ableitung Höhenprofil

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ExtracTopoOb-Profil.png" alt="Höhenprofil aus DGM  Türlersee (GITTA 2005)" caption="*Höhenprofil aus DGM  Türlersee (GITTA 2005)*" %}

Auf Grundlage eines digitalen Geländemodells können durch Extraktion der Höhenwerte *Profile* zwischen zwei Punkten berechnet werden. Derartige Profile sind in vielen anwendungsorientierten Fragestellungen relevant, z. B. für die Planung im Straßenbau oder als Sichtlinien (Seilbahnen, Funkverbindungen). Erweitert man dieses Konzept können alle räumlich verteilten Informationen auf einer direkten also geometrisch kürzesten Verbindungen analysiert und dargestellt werden


### Ableitung Profilllinie als Pauschalgefälle

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ExtracTopoOb-PauschalG.png" alt="Pauschalgefälle aus DGM  Türlersee (GITTA 2005)" caption="*Pauschalgefälle aus DGM  Türlersee (GITTA 2005)*" %}

Das *Pauschalgefälle* ist eine weitere Ableitung aus der Profillinie. Es beschreibt die mittlere Neigung zwischen zwei Punkten im Gelände und ist folglich skalenabhängig. Ein wichtiges Anwendungsgebiet ist die einfache Abschätzung von Sturz-Prozessen (Steinschlag, Eisschlag).

### Falllinie

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ExtracTopoOb-Falllinie.png" alt="Falllinie aus DGM  Türlersee (GITTA 2005)" caption="*Falllinie aus DGM  Türlersee (GITTA 2005)*" %}

In einem digitalen Geländemodell kennzeichnet die *Falllinie*, ausgehend von einem beliebigen Punkt, den Pfad (=verknüpfte Einzelstrecken) entlang dessen die Schwerkraft wirkt (=Vektor Oberlieger-Unterlieger). Oder konkret ausgedrückt den Weg des fließenden Wassers oder rollenden Steins. So können u. a. zur Modellierung von Eis- und Steinschlag, aber auch für die Berechnung von Einzugsgebieten verwendet werden. Erweitert man dieses Konzept indem z.B. statt Höhenwerte in Metern Kosten in Euro als “Kostengebirge” aufgefasst werden, Können so Pfade geringster Kosten (oder Widerstands) bestimmt werden.




### Wassereinzugsgebiete

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ExtracTopoOb-catchment.png" alt="Wassereinzugsgebiet aus DGM (GITTA 2005)" caption="*Wassereinzugsgebiet auf der Grundlage eines DGM (GITTA 2005)*" %}

Die Ableitung von *Wassereinzugsgebieten* aus digitalen Geländemodellen nutzt das Konzept der Falllinie. Vernetzt man alle Falllinien die einen gemeinsamen Unterlieger als Ausflusspunkt haben und grenzt diesen Raum ab so erzeugt man ein durch die Oberflächenmorphologie determiniertes Wassereinzugsgebiet. Solche Wassereinzugsgebiete sind eine wichtige Komponente in vielen hydrologischen, geomorphologischen und landschaftskundlichen GIS-Anwendungen.



Die zuvor angesprochenen Beipiele sollen einen Eindruck von der Vielfältigkeit der Informationsgewinnung durch **Ableitungen** vermitteln. In der nachfolgenden Tabelle wird ein Überblick über weitere Informationsprodukte, die aus Geländemodellen ableitbar sind gegeben. Dieser Überblick ist keineswegs vollständig. Vielmehr stellt er in willkürlicher Mischung unterschiedliche Stufen der Ableitung zusammen. Versuchen Sie herauszufinden welche Information eine Ableitung erster bzw. zweiter Ordnung ist.

| Information | Output-Typ | Beschreibung |
| Neigung            | Zahl      | Neigung an einem Punkt |
| Pauschalgefälle    | Zahl      | Gefälle zwischen zwei Punkten |  
| Exposition         | Zahl      | Ausrichtung des Hanges |
| Kurvatur           | Zahl      | Krümmung in eine bestimmte Richtung (z. B. Plan- oder Profilkurvatur) |
| Intervisibilität   | Ja/ Nein  | Gibt an, ob der Betrachter einen bestimmten Punkt sehen kann |
| Sichtbares Gebiet  |Polygone   | Gebiet, welches von einem oder mehreren Punkten aus sichtbar ist | 
| Reliefschatten     | Bild      |Schattenwurf durch das Gelände bei einer bestimmten Sonnenposition |
| Flussnetzwerk      | Linien    |/|
| Einzugsgebiete            | Polygone   |/|
| Profil             | Linie     | Höhenprofil entlang einer bestimmten Linie |
| Volumen            | Zahl      | Füllungs- oder Abtragsvolumen für ein Gebiet und für eine bestimmte Höhe |
| Perspektivische Abbildung      | Bild      |/|
| Falllinie          | Linie     | Pfad entlang der steilsten Neigung |

