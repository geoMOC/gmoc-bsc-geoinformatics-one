---
title: – Funktionale Ableitungen 
toc: true
toc_label: Inhalt




panel0:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/slope.png
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/slope.png
    title: "Formel zur Berechnung der HAnneigung im Raster"
    alt: "Formel zur Berechnung der HAnneigung im Raster"

panel1:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/neigung_dy.png
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/neigung_dy.png
    title: "dy"
    alt: "dy"

panel2:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/neigung_aufsicht.png
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/neigung_aufsicht.png
    title: "NAchbarschaft"
    alt: "NAchbarschaft"

panel3:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/aspect.png
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/aspect.png
    title: "Exposition"
    alt: "Exposition"

panel4:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/aspect_a.png
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/formula/aspect_a.png
    title: "Exposition Faktor a"
    alt: "Exposition Faktor a"


---


Das Phänomen Gelände spielt in vielen räumlichen Vorstellungen eine zentrale Rolle. Diese reicht von der kognitiven Wahrnehmung z.B. der Frage *Was ist ein Wanderweg?* (vgl. Abbildung) bis zur zuvor skizzierten formalen, quantitativen Ableitung von Eigenschaften.
In einem GIS werden die Informationen über die Form einer Geländeoberfläche in der Regel aus Höheninformationen abgeleitet. Diese Höheninformation wird in einem digitalen Geländemodell (DGM) gespeichert. Digitale Geländemodelle bestehen zunächst nur aus einer spezifischen Höheninformation für einen definierten Raumausschnitt (Rasterzelle, Punkt, Polygon). Auf der Basis dieser Primärinformation werden zahlreiche zusätzliche Informationen abgeleitet. Nachfolgend sollen am Beispiel der Hangneigung, Exposition und Kurvatur skizziert werden, wie die Ableitungen mit Hilfe von Funktionen berechnet werden. Entscheidend ist weniger die verwendete Mathematik als vielmehr die resultierenden Informationen, die für die unterschiedlichsten Fragestellungen verfügbar ist.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/terrainmatters.jpg" alt="Das Phänomen Gelände spielt häufig eine zentrale Rolle nicht nur auf Wanderwegen sondern auch in der skalenabhängigen Analyse von Oberflächenstrukturen, Standorten Versorgungsleitungen und vieles mehr (gis-ma 2009)" caption="*Das Phänomen Gelände spielt häufig eine zentrale Rolle nicht nur auf Wanderwegen sondern auch in der skalenabhängigen Analyse von Oberflächenstrukturen, Standorten Versorgungsleitungen und vieles mehr (gis-ma 2009)*" %}


### Hangneigung

Auf einer (Gelände-)Oberfläche ist die Neigung (oder auch: Hangneigung) an einem Punkt gegeben durch die Tangentialebene. Das steilste Gefälle auf dieser Tangentialebene bezeichnet man als Neigung (engl. slope). Die Neigung lässt sich aus den Ableitungen der Oberfläche in der Richtung der x-Koordinate und derjenigen in Richtung der y-Koordinate berechnen.

Um die Neigung aus einem Höhenmodell zu berechnen, braucht man daher eine Methode, mit der man Ableitungen aus den Höhenwerten schätzen kann. Die gängigste Art, dies für ein *gitterbasiertes Geländemodell* zu tun, ist unter dem Namen „finite Differenzen“ bekannt (Horn 1981).

Um das Prinzip der finiten Differenzen zu erläutern, sei zuerst auf den eindimensionalen Fall eines Profils (statt einer Oberfläche) zurückgegriffen. Die folgende Abbildung zeigt, wie durch Bildung des Quotienten der Differenzen der Höhe (dz) und in der Ebene (dx) zuerst die erste Ableitung (Slope), und davon ausgehend die zweite Ableitung (Curvature) geschätzt werden kann. Die gewählte Schrittweite in x-Richtung ist in diesem Fall gleich 4. Das heißt, es wird die finite Differenz bezgl. der beiden zweiten Nachbarn nach links bzw. nach rechts vom zentralen Punkt aus gebildet. Diesem zentralen Punkt wird sodann der Wert der Ableitung zugewiesen. In der Abbildung sind der Zentralpunkt sowie dz und dx entsprechend rot markiert.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/Geomorphomet-hsc.png" alt="finite Differenzen"  %}

Für den zweidimensionalen Fall einer Oberfläche gibt (Horn 1981) die Formeln zur Schätzung der Neigung mittels finiten Differenzen:

{% include gallery id="panel0"   layout = "half"  %}

**mit**

{% include gallery id="panel1"   layout = "half"  %}



Die Nummerierung der Punkte in der 3-3-Nachbarschaft um den Zentralpunkt (z5) zur Bildung der Differenzen ist aus der nachstehenden Abbildung ersichtlich. In den Formeln der finiten Differenzen oben fällt auf, dass die Differenzen, die durch den Zentralpunkt führen, doppelt gewichtet sind.


{% include gallery id="panel2"   layout = "third"  %}


### Exposition

Unter Exposition (engl. aspect) versteht man die Richtung (im Uhrzeigersinn von Norden = Azimut) des steilsten Gefälles der Tangentialebene oder einfacher die Ausrichtung des Hanges zur Himmelsrichtung. Wiederum benötigt man die Ableitungen in x- und y-Richtung zur Berechnung, wie sie für die Berechnung der Hangneigung schon gebildet wurden (Horn 1981):

{% include gallery id="panel3"   layout = "half"  %}


**mit**


{% include gallery id="panel4"   layout = "third"  %}

Zusätzlich muss man für die Berechnung unterscheiden, ob die Werte dieser Ableitungen negativ, null oder positiv sind.

### Krümmung

Die Kurvatur (engl. curvature) oder Krümmung  ist die zweite Ableitung einer Oberfläche an einem bestimmten Punkt in eine bestimmte Richtung.
Bei digitalen Geländemodellen sind insbesondere die *Profilkurvatur* (Kurvatur in Richtung des steilsten Gefälles) und die *Plankurvatur* (Kurvatur in Richtung der Höhenlinie) von besonderem Interesse. Die Kurvaturwerte sind bei Konvexität (erhabene Formen) negativ und positiv bei Konkavität (Hohlformen).

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/TIN3D.png" alt="Exposition" %}



