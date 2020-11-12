---
title: – Prozessorientierte Ableitung von Informationen 
toc: true
toc_label: Inhalt


panel1:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/keyboardnumbers.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/keyboardnumbers.gif
    title: " Lokale Abflussrichtungen in einem Raster können mit den Ziffern einer Tastatur kodiert werden (GITTA 2005)"
    alt: "Lokale Abflussrichtungen in einem Raster können mit den Ziffern einer Tastatur kodiert werden (GITTA 2005)"

panel2:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/D8Algorithm.jpg
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/D8Algorithm.jpg
    title: "D8 Formel"
    alt: "D8 Formel"

panel3:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/Upstream_Formula.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/Upstream_Formula.gif
    title: "Oberlieger  Formel"
    alt: "Oberlieger Formel"

panel4:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/Wetness_Formula.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/Wetness_Formula.gif
    title: "Wetness  Formel"
    alt: "Wetness Formel"

panel5:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/StreamPower_Formula.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/StreamPower_Formula.gif
    title: "Stream Power Formel"
    alt: "Stream Power Formel"

panel6:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/Sediment_Formula.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/Sediment_Formula.gif
    title: "Sediment_Formula Formel"
    alt: "Sediment_Formula Formel"

---







Die Basis für die Ableitung vieler hydrologischer Parameter ist ein Gewässernetz, das manuell digitalisiert oder automatisch aus einem digitalen Geländemodell extrahiert werden kann. Lokale Abflussrichtungen in Rastern werden oft nach dem Zifferblock einer Tastatur kodiert. Ein Rasterpunkt (Pixel), von dem Wasser in Richtung Südwesten abfließt, hätte demnach den Wert 1, wobei ein Pixel mit der Abflussrichtung Westen den Wert 4 hätte, usw.

{% include gallery id="panel1"  caption= "Lokale Abflussrichtungen in einem Raster können mit den Ziffern einer Tastatur kodiert werden (GITTA 2005)" layout = "third"  %}


Eine Karte, die die lokale Abflussrichtung für jeden Rasterpunkt enthält, wird als lokales Netz der Fließrichtung (local drain direction net bzw. ldd net) bezeichnet (Burrough et al. 1998). Es gibt zahlreiche Algorithmen um LDD-Netze zu berechnen; jede geht von einer anderen Ausnahme über den Wasserabfluss im Gelände aus. Für eine (interaktive) Vertiefung sei auf die Software Landserf von (Wood 2005) verwiesen.

## D8 Algorithmus

Der einfachste und bekannteste ist der sogenannte D8-Algorithmus der auf der Annahme beruht, dass, in einer Umgebung von neun Rasterpunkten, das Wasser in Richtung der steilsten Neigung abfließt. Es wird dazu die Neigung zu jedem der acht umliegenden Punkten von einem zentralen Quellpunkt mit folgender Formel errechnet:

{% include gallery id="panel2"   layout = "third"  %}


wobei d die Entfernung und Δz der Höhenunterschied zwischen den zwei Punkten ist. In einem Raster, bei dem die Pixelbreite 1 beträgt, müssen wir zwischen folgenden zwei Fällen unterscheiden:

*  Wenn wir die Neigung in Richtung Norden, Osten, Süden oder Westen errechnen, beträgt die Entfernung zwischen den Rasterpunkten d = 1.
*  Wenn wir die Neigung in die diagonalen Richtungen (Nordosten, Südosten, Südwesten, Nordwesten) berechnen wollen, ist die Distanz d zwischen den Rasterpunkten Wurzel(2).

### Das lokale Netz der Fließrichtung (LDD-Netz)

Nun wissen wir, wie die Abflussrichtung für einen einzelnen Punkt in der Mitte einer Nachbarschaft von neun Punkten errechnet wird. Indem dieser Ausschnitt als Fenster schrittweise über die gesamte Rastermatrix bewegt wird, können wir jedem Punkt eine lokale Abflussrichtung zuweisen und so ein LDD-Netz erstellen.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/ldd_clarify.gif" alt="LDD-Netz für ein kleines DGM (links) Lokale Abflussrichtungen sind als Pfeile gekennzeichnet, (Rechts) Lokale Abflussrichtungen nach dem Zeichenblock einer Tastatur gekennzeichnet" caption="*LDD-Netz für ein kleines DGM (links) Lokale Abflussrichtungen sind als Pfeile gekennzeichnet, (rechts) Lokale Abflussrichtungen nach dem Zeichenblock einer Tastatur gekennzeichnet*" %}


### Beispiel Türler See

Die nachfolgende Abbildung der Abflussrichtungen zeigt ein 25m-Raster-DGM vom Türlersee-Gebiet und das davon abgeleitete LDD-Netz. Die Seefläche im Süden der Karte muss aus dem Verfahren ausgeschlossen werden, weil die Fließrichtung einer horizontalen Ebene undefiniert ist.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/flowDirection_look.gif" alt="Abflussrichtungen, die von einem 25m-Raster-DGM mit einem D8-Algorithmus errechnet wurden. (Swisstopo 1991)" caption="*Abflussrichtungen, die von einem 25m-Raster-DGM mit einem D8-Algorithmus errechnet wurden. (Swisstopo 1991)*" %}


Analog dazu kann ein ldd net in einen Vektordatensatz transformiert und entsprechend visualisiert werden.


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/lddnetLook.gif" alt="Ein LDD-Netz als Vektorkarte" caption="*Ein LDD-Netz als Vektorkarte*" %}


 
## Abgeleitete Informationen aus Abflussnetzwerken


Lokale Abflussnetzwerke sind zunächst nur zur Bestimmung der direkten Ober- und Unterlieger sinnvoll. Wie jedoch bereits im Kapitel Abgeleitete Informationen skizziert wurde, können solche ersten Ableitungen für weitere Informationsgewinnung sehr hilfreich sein. Falls für jedes Pixel bekannt ist von wie sich gravitative Zu- und Abflüsse verhalten können zum Beispiel alle Elemente gezählt oder markiert werden, die von einem bestimmten Pixel aus flussauf(ab)wärts liegen. Gleichgültig ob die räumliche Verteilung von Niederschlag als gleichmäßig oder variabel angenommen wird, kann mit dieser Information berechnet werden, wie viel Wasser sich in jedem Pixel ansammelt. Ein LDD-Netz kann in einer Vielzahl von spezifischen hydrologischen Analysen eingesetzt werden. Eine naheliegende Anwendung ist die Berechnung von flussaufwärts liegenden Elementen zur Ableitung von Einzugsgebieten, Wasseransammlung, Kämmen oder Flussbetten. Es gibt darüberhinaus zahlreiche weitere hydrologische Indikatoren. Die wichtigsten sind:

*  Feuchtigkeitsindex (Wetness Index, CTI)
*  Flussintensitätsindex (Stream Power Index, SPI)
*  Sedimenttransportindex (Sediment Transport Index, STI)

### Elemente die flussaufwärts liegen

Die Fläche, die flussaufwärts liegt, ist ein wichtiger Faktor in der Berechnung von Stofftransporten. Die Anzahl der Elemente, die von einem bestimmten Pixel flussaufwärts liegen, lässt sich leicht mit der folgenden Formel berechnen.

{% include gallery id="panel3"  layout = "third"  %}

Wobei `ci` der i-te Rasterpixel mit dem Wert `S(ci)` und `SUM(cu)` die Summe aller Elemente beträgt, von denen Wasser in `ci` abfließt. Natürlich können die flussaufwärtsliegenden Elemente je nach Fragestellung gewichtet werden. Zur Berechnung von Wasseransammlung kann die Gewichtung z.B. ein Gleichgewicht darstellen zwischen lokaler Niederschlagsmenge und dem Wasser, das durch Evaporation, Infiltration und Interzeption der Oberfläche verlorengeht.

In der nächsten Abbildung sieht man oben links ein LDD-Netz. Zusätzlich wird ein Indexwert für jedes Pixel vergeben (Raster oben rechts). Auf dieser Grundlage werden die flussaufwärtsliegenden Elemente für jedes Pixel gefunden und mit der Liste der Indexwerte identifiziert (Mitte links). Falls zusätzlich eine Gewichtung verwendet wird (Mitte rechts), entsteht das Einzugsgebietraster, das für jedes Pixel die Anzahl der flussaufwärtsliegenden Elemente aufweist (unten).

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/flowaccumulation2_clarify.gif" alt="Berechnung der Anzahl von flussaufwärtsliegenden Elementen für jedes Pixel." caption="*Berechnung der Anzahl von flussaufwärtsliegenden Elementen für jedes Pixel.*" %}


### Kanäle und Kämme

In der nachstehenden Abbildung wurden die flussaufwärtsliegenden Elemente für ein DGM berechnet. Das sichergebende Muster, korrespondiert weitgehend mit dem Flussnetz auf der entsprechenden topographischen Karte, da ein wasserführendes Pixel erst dann “sichtbar” wird fall es eine genügend große Zahl von Oberliegern aufweist.

Die zuvor abgeleitete Rastermatrix der absoluten Wasseransammlungen kann durch Verwendung eines Schwellenwerts zu einer Rastermatrix Karte der Wasserläufe und Kämme reklassifiziert werden. Eine solche Matrix enthält nur boolesche Werte, das heißt, ein Pixel gehört entweder zu einem Fließgewässer bzw. Kamm oder weist keine Information auf. 


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/upstreamElements.gif" alt="Wasseransammlungen können anhand eines ldd nets errechnet werden. (Swisstopo 1991)" caption="*Wasseransammlungen können anhand eines ldd nets errechnet werden. (Swisstopo 1991)*" %}


Die Wahl sinnvoller Schwellenwerte ist abhängig von der Qualität des DGM und der räumlichen Auflösung. Solche Analyseabfragen zur Bestimmung von Wasserläufen können in Pseudo-Abfragesprache z.B. lauten:

``if(upstreamelements >= 50) then streams=true else streams=false;``

Die Berechnung von Kämmen in einem Raster kann als zweiseitiges Problem einer Wasserlaufberechnung betrachtet werden. Kämme sind per Definition Pixel, die keine flussaufwärtsliegenden Elemente besitzen (Brändli 1997). Die Abfrage in Pseudo-Abfragesprache:

``if(upstreamelements = 0) then kaemme=true; else kaemme=false;``

 
### Feuchtigkeitsindex (Wetness Index)

Eine Karte der flussaufwärtsliegenden Elemente kann für weitere wichtige hydrologische Konzepte bzw. inhaltlich/thematische Fragestellungen herangezogen werden. Ein gutes Beispiel stellt der Feuchtigkeitsindex dar (siehe Beven and Kirkby zit. n. (Burrough et al. 1998).

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/wetnessIndex.gif" alt="Der aus dem ldd net abgeleitete Feuchtigkeitsindex. (Swisstopo 1991)" caption="*Der aus dem ldd net abgeleitete Feuchtigkeitsindex. (Swisstopo 1991)*" %}

{% include gallery id="panel4"  layout = "third"  %}

wobei As die flussaufwärtsliegende Fläche und ß die Neigung jedes Pixels wiedergeben (vgl. Abbildung). Deutlich erkennbar ist die aus der Empirie bekannte relative Trockenheit der Kämme und Feuchte der Akkumulationsgebiete zu erkennen.

 
### Flussintensitätsindex (Stream Power Index)

Der Flussintensitätsindex (Burrough et al. 1998), der durch die untenstehende Gleichung berechnet wird, ist ein Maß für das Erosionspotential des Oberflächenabfluss.


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/streamPowerIndex.gif" alt="Das vom ldd net abgeleitete Flussintensitätsindex. (Swisstopo 1991)" caption="*Der vom ldd net abgeleitete Flussintensitätsindex. (Swisstopo 1991)*" %}


{% include gallery id="panel5"  layout = "third"  %}



As stellt die flussaufwärtsliegende Fläche dar; ß steht für die Neigung jedes Pixels. In der folgenden Abbildung sehen Sie, dass die Flussintensitätsindexkarte der Karte der flussaufwärtsliegenden Elemente ähnelt.

 
### Sedimenttransportindex (Sediment Transport Index)

Der Sedimenttransportindex beschreibt den Prozess der Erosion/Denudation und Ablagerung. Im Gegensatz zum Länge-Neigung-Faktor in der Universalbodenverlustgleichung (Universal Soil Loss Equation, USLE), kann man den Sedimenttransportindex auf dreidimensionale Flächen anwenden (Burrough et al. 1998).


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/sedimentTransportIndex.gif" alt="Der vom ldd net abgeleitet Sedimenttransportindex . (Swisstopo 1991)" caption="*Der vom ldd net abgeleitet Sedimenttransportindex . (Swisstopo 1991)*" %}


{% include gallery id="panel6"  layout = "third"  %}

Der Sedimenttransportindex wird mit folgender Gleichung errechnet. As ist die Fläche, die von jedem Pixel flussaufwärts liegt, und ß ist die Neigung des Pixels. Die nachstehende Abbildung zeigt ein Beispiel einer Sedimenttransportindexkarte. Die flussaufwärtsliegende Fläche wird stärker gewichtet als die Neigung. Dadurch wird das Ergebnis entsprechend modifiziert.

 
### Maximale Fließweglänge (Maximum flow-path length)

Der maximale Fließweg ist die Länge des längsten Fließwegs von der Grenze des Einzugsgebietes zu einem beliebigen Punkt im DGM. Statt Fläche anzusammeln, wie es für flussaufwärtsliegende Flächen gemacht wurde, wird der Weg angesammelt, den Wasser hinter sich lässt, wenn es von Pixel zu Pixel fließt. Nur der längste Fließweg aller flussaufwärtsliegenden Pixel wird an das flussabwärtsliegende Pixel gegeben, nicht die Summe aller Fließwege (Wilson et al. 2000).
Maximaler Fließweg in Meter zu jedem flussaufwärts vorhandenen Pixel.


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/maximumFlowPathLength.gif" alt="Maximaler Fließweg in Meter zu jedem flussaufwärts vorhandenen Pixel. (Swisstopo 1991)" caption="*Maximaler Fließweg in Meter zu jedem flussaufwärts vorhandenen Pixel. (Swisstopo 1991)*" %}

Die obenstehende Abbildung zeigt ein Beispiel für den längsten Fließweg. Natürlich haben Hügel und Kämme niedrige Werte, wobei der Wert in einem Wasserlauf flussabwärts kontinuierlich zunimmt.


## Denken Sie mit...

Die Indizes, die oben beschrieben wurden, beruhen auf der Anzahl der flussaufwärtsliegenden Elemente, die wir leicht berechnen können. Das Gegenteil (die Anzahl von Elementen, die flussabwärts von einem Element liegen) könnte aber auch interessant sein. Stellen Sie sich vor, Sie möchten die Entfernung von einer beliebigen Position zur Einmündung des nächsten Seitenbaches  berechnen.

* Wie würden Sie vorgehen, ohne die schon bekannten Algorithmen anzupassen?
 





